<template>
  <div class="game-container">
    <h1><span class="true">True</span> or <span class="false">False</span>?</h1>
    <div v-if="gameWin">
      <h1 class="true">😳🕺 Wow! You Win The Game! Congratulations!</h1>
    </div>
    <div v-if="gameOver">
      <h1>Sorry! The game is over! Want to try again?</h1>
      <el-button @click="startGame">New Game</el-button>
    </div>
    <div v-if="questions.length && !gameOver && !gameWin" v-loading="isLoading">
      <GameInfo
        :difficulty="currentQuestion.difficulty"
        :points="points"
        :questions-left="questions.length - questionIndex"
      />
      <Question :text="currentQuestion.question" />
      <Answers
        @correctAnswer="onCorrectAnswer"
        @wrongAnswer="onWrongAnswer"
        :correctAnswer="currentQuestion.correct_answer === 'True'"
      />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Question from './Question'
import Answers from './Answers'
import GameInfo from './GameInfo'

export default {
  name: 'GameContainer',
  components: { Question, Answers, GameInfo },
  data () {
    return {
      questionsCount: 5,
      questions: [],
      questionIndex: 0,
      isLoading: true,
      points: 0,
      gameOver: false,
      gameWin: false
    }
  },
  computed: {
    currentQuestion () {
      return this.questions[this.questionIndex]
    }
  },
  mounted () {
    this.startGame()
  },
  methods: {
    startGame () {
      this.gameOver = false
      this.loadData()
      this.questionIndex = 0
      this.points = 0
    },
    async loadData () {
      this.isLoading = true
      const res = await axios.get(`https://opentdb.com/api.php?amount=${this.questionsCount}&category=9&type=boolean`)
      this.isLoading = false
      this.questions = res.data.results
    },
    onCorrectAnswer () {
      this.$notify.success({
        title: 'Success',
        message: 'Great! 🤩 Right Answer!',
        duration: 1500
      })
      this.questionIndex++
      this.points++
      if (this.questionIndex === this.questions.length - 1) {
        this.gameWin = true
      }
    },
    onWrongAnswer () {
      this.$notify.error({
        title: 'Oops',
        message: 'it was a wrong answer 😢 Good luck for you next time!',
        duration: 1500
      })
      this.gameOver = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  h1  {
    margin-top: 80px;
    margin-bottom: 50px;
  }
  .el-notification {
    font-family: 'Avenir', Helvetica, Arial, sans-serif !important;
  }
  .true {
    color: #67C23A;
  }
  .false {
    color: #f56C6C;
  }
</style>
