<script>
  import "./+page.css";
  import Keyboard from "../components/Keyboard.svelte";
  import Man from "../components/Man.svelte";
  import Word from "../components/Word.svelte";
  import words from "../data/wordList.json"; // File from https://github.com/WebDevSimplified/react-hangman/blob/main/src/wordList.json

  let sentence;
  let arr;
  let left;
  let checked;
  let missCount;
  let ended;
  let win;

  const getWord = () => {
    sentence = words[Math.floor(Math.random() * words.length)];
  };
  getWord();

  const init = () => {
    arr = sentence.split("");
    left = arr;
    left = left.filter((i) => i !== " ");
    checked = [];
    missCount = 0;
    ended = false;
    win = "";
  };
  init();

  const handleKey = (key) => {
    checked = [...checked, key];
    if (!left.includes(key)) {
      missCount++;
    }
    left = left.filter((i) => i !== key);
    if (left.length === 0) {
      ended = true;
      win = "You won";
      console.log("wygrana");
    }
    if (missCount === 10) {
      ended = true;
      win = "You Lost";
      console.log("przegrana");
    }
  };

  const handleReset = () => {
    getWord();
    init();
  };
</script>

<Man {missCount} {ended} {win} {handleReset} />
<Word {arr} {checked} {ended} />
<Keyboard {checked} {handleKey} {ended} />
