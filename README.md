# Ya-hochu
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Heart</title>

<style>
    body{
        margin:0;
        background:#000;
        display:flex;
        justify-content:center;
        align-items:center;
        height:100vh;
        overflow:hidden;
        font-family:Consolas, monospace;
    }

    pre{
        color:#ff2b55;
        font-size:15px;
        line-height:1;
        white-space:pre;
        text-shadow:
            0 0 5px #ff0033,
            0 0 12px #ff0033,
            0 0 20px #ff0033;
    }
</style>
</head>

<body>

<pre id="output"></pre>

<script>
const output = document.getElementById("output");

const heart = [
"                  я хочу            я хочу",
"               букет я хочу      букет я хочу",
"           букет я хочу букет  букет я хочу букет",
"       я хочу букет я хочу букет я хочу букет я хоч",
"     букет я хочу букет я хочу букет я хочу букет я х",
"      я хочу букет я хочу букет я хочу букет я хочу",
"         букет я хочу букет я хочу букет я хочу",
"              букет я хочу букет я хочу букет",
"                   я хочу букет я хочу",
"                        букет букет",
"                            ♥ ♥",
"                             ♥"
];

let text = "";

// ~15 секунд на всю анимацию
const totalChars = heart.join("\n").length;
const speed = 15000 / totalChars;

async function typeLine(line){
    for(const char of line){
        text += char;
        output.textContent = text;

        await new Promise(r => setTimeout(r, speed));
    }

    text += "\n";
    output.textContent = text;
}

async function start(){
    for(const line of heart){
        await typeLine(line);
    }
}

start();
</script>

</body>
</html>
