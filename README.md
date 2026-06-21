import { useState } from "react";

const phrases = [
  "No",
  "whyy??",
  "final answer???",
  "I'll be angry at you!",
  "click yes Please:(",
  "I'm gonna cry...",
  "You are breaking my heart:(",
];

function App() {
  const [noCount, setNoCount] = useState(0);
  const [yesPressed, setYesPressed] = useState(false);
  const yesButtonSize = noCount * 20 + 16;

  function handleNoClick() {
    setNoCount(noCount + 1);
  }

  function getNoButtonText() {
    return phrases[Math.min(noCount, phrases.length - 1)];
  }

  const containerStyle = {
    display: "flex",
    flexDirection: "column",
    alignItems: "center",
    justifyContent: "center",
    height: "100vh",
  };

  return (
    <div style={containerStyle}>
      {yesPressed ? (
        <>
          <img
            alt="bear with heart"
            src="https://media1.tenor.com/m/spboQdmfx9oAAAAC/hugs-t-quelo.gif"
          />
          <div className="text">Love youuuu</div>
        </>
      ) : (
        <>
          <img
            alt="Love GIF"
            src="https://media1.tenor.com/m/vDnz6cX_JdkAAAAC/%E0%B8%94%E0%B8%AD%E0%B8%81%E0%B8%A1%E0%B8%B1%E0%B9%89-flowers.gif"
          />
          <div>Will you be my valentine?</div>
          <div>
            <button
              className="yesButton"
              style={{
                fontSize: yesButtonSize,
                backgroundColor: "green",
                color: "white",
                border: "none",
                padding: "10px 20px",
                margin: "5px",
                cursor: "pointer",
                borderRadius: "5px",
              }}
              onClick={() => setYesPressed(true)}
            >
              Yes
            </button>
            <button
              onClick={handleNoClick}
              className="noButton"
              style={{
                backgroundColor: "red",
                color: "white",
                border: "none",
                padding: "10px 20px",
                margin: "5px",
                cursor: "pointer",
                borderRadius: "5px",
              }}
            >
              {getNoButtonText()}
            </button>
          </div>
        </>
      )}
    </div>
  );
}

export default App;
