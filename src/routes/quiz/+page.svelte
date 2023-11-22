<script lang="ts">
    type Question = {
        question: string;
        isYesOk: boolean;
    }

    const questions: Question[] = [
        {
            question: "Are you 16 - 65 years old?",
            isYesOk: true,
        },
        {
            question: "Do you currently weigh less than 50kg (12 pounds)?",
            isYesOk: false,
        },

        {
            question: "Have you had a blood or blood product transfusion since 1 January 1980?",
            isYesOk: true
        },
    ];
    function fail() {
        location.href = "/quiz/fail";
    }
    let currentQuestionIndex = 0;
    function t() {
        if(currentQuestionIndex === questions.length - 1) {
            // go to the next page
            location.href = "/quiz/success";
        } else {
            currentQuestionIndex++
        }
    }
    $: currentQuestion = questions[currentQuestionIndex];
</script>

<div class="quiz">

    <div class="blocks">
            <div class="block">
                <div class="header">{currentQuestion.question}</div>
                <div class="main-btn" on:click={() => {
                    if(!currentQuestion.isYesOk) {
                        fail();
                        return;
                    }
                    t();
                }}>Yes</div>
                <div class="main-btn" on:click={() => {
                     if(currentQuestion.isYesOk) {
                        fail();
                        return;
                    }
                    t();
                }}>No</div>
            </div>
    </div>
    <div class="nav">

        <div class="steps">
            <div class="step active"></div>
            <div class="step"></div>
            <div class="step"></div>
        </div>

        <button class="button" disabled>Next</button>
    </div>
</div>

<style lang="scss">
  .steps {
    display: flex;
    gap: 16px
  }
  .step {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;

    &::after {
      content: "";
      display: block;
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background: #A8ACB8;
    }


    &.active {
      background: rgb(168, 172, 184, 0.2);
    }
  }
  .block {
    display: flex;
    flex-direction: column;
    padding: 20px;
    margin-top: 70px;
    gap: 16px;

    .header {
      margin-bottom: 40px;
      color: rgba(18, 18, 18, 0.80);

      font-size: 24px;
      font-style: normal;
      font-weight: 500;
      line-height: 150%; /* 36px */
      letter-spacing: -0.456px;
    }
  }

  .main-btn {
    min-height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
    border: 2px solid #F1F1F3;
    color: #121212;
    background: #FFFFFF;

    text-align: center;
    font-size: 10px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px; /* 200% */
    text-transform: uppercase;

    &:hover, &:active {
      color: #ffffff;
      background: #121212;
    }
  }
    .quiz {
      display: flex;
      flex-direction: column;
      height: 100dvh;
    }

    .nav {
      margin-top: auto;
      display: flex;
      padding: 20px;
      align-items: center;
    }

    .button {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 16px 20px;
      min-width: 160px;
      color: #FFF;
      border-radius: 6px;
      background: #000000;
      font-size: 14px;
      font-weight: 700;
      line-height: 150%;
      border: none;

      margin-left: auto;

      &[disabled] {
        background: #A8ACB8;
      }
    }
</style>
