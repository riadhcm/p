document.addEventListener('DOMContentLoaded', () => {
  const timerDisplay = document.getElementById('timer-display');
  const startBtn = document.getElementById('start-btn');
  const resetBtn = document.getElementById('reset-btn');
  const shortBreakBtn = document.getElementById('short-break-btn');
  const longBreakBtn = document.getElementById('long-break-btn');

  let pomodoroTime = 25 * 60; // 25 minutes
  let timeRemaining = pomodoroTime;
  let timerInterval = null;
  let isRunning = false;
  let currentMode = 'pomodoro'; // 'pomodoro', 'short-break', 'long-break'

  function formatTime(seconds) {
    const minutes = Math.floor(seconds / 60);
    const remainingSeconds = seconds % 60;
    return `${minutes.toString().padStart(2, '0')}:${remainingSeconds.toString().padStart(2, '0')}`;
  }

  function updateDisplay() {
    timerDisplay.textContent = formatTime(timeRemaining);
  }

  function startTimer() {
    if (isRunning) return;
    isRunning = true;
    timerInterval = setInterval(() => {
      if (timeRemaining > 0) {
        timeRemaining--;
        updateDisplay();
      } else {
        clearInterval(timerInterval);
        isRunning = false;
        alert('Time’s up!');
        if (currentMode !== 'pomodoro') {
          currentMode = 'pomodoro';
          timeRemaining = pomodoroTime;
          updateDisplay();
        }
      }
    }, 1000);
  }

  function resetTimer() {
    clearInterval(timerInterval);
    isRunning = false;
    currentMode = 'pomodoro';
    timeRemaining = pomodoroTime;
    updateDisplay();
  }

  function setBreak(minutes, mode) {
    clearInterval(timerInterval);
    isRunning = false;
    timeRemaining = minutes * 60;
    currentMode = mode;
    updateDisplay();
  }

  startBtn.addEventListener('click', startTimer);
  resetBtn.addEventListener('click', resetTimer);
  shortBreakBtn.addEventListener('click', () => setBreak(5, 'short-break'));
  longBreakBtn.addEventListener('click', () => setBreak(10, 'long-break'));

  updateDisplay();
});
