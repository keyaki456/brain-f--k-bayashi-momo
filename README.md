<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />
    <title>stlite app</title>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@stlite/mountable@0.73.1/build/stlite.css"
    />
  </head>
  <body>
    <div id="root"></div>
    <script src="https://cdn.jsdelivr.net/npm/@stlite/mountable@0.73.1/build/stlite.js"></script>
    <script>
stlite.mount(
  {
    requirements: [],
    entrypoint: "streamlit_app.py",
    files: {
"streamlit_app.py": `import streamlit as st
import time

st.title("BrainFuck林もも")
text = st.text_area("Your BrainFuck林もも code here", "おっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱい妹ちゃんボロンボロンボロン妹ちゃんおっぱいおっぱいおっぱいおっぱいおっぱいおっぱいおっぱい妹ちゃん妹ちゃんおっぱいおっぱいおっぱい妹ちゃん")
input = st.text_input("標準入力(ありばや進数で入力してください)","外星人かわいい")

on = st.toggle("←runボタン。これがonの間、有林が働き続ける。")

cells = [0] * 256
cursol=0
workinghayashi=0
nyuuryokubayashi=0
output=""
tmpcount=0

aribayashiturple=("0","1","2","3","4","5","6","7","8","9",
                  "a","b","c","d","e","f","g","h","i","j",
                  "k","l","m","n","o","p","q","r","s","t",
                  "u","v","w","x","y","z","A","B","C","D",
                  "E","F","G","H","I","J","K","L","M","N",
                  "O","P","Q","R","S","T","U","V","W","X",
                  "Y","Z","あ","い","う","え","お","か","き","く",
                  "け","こ","さ","し","す","せ","そ","た","ち","つ",
                  "て","と","な","に","ぬ","ね","の","は","ひ","ふ",
                  "へ","ほ","ま","み","む","め","も","や","ゆ","よ",
                  "ら","り","る","れ","ろ","わ","を","ん","有","林",
                  "栗","川","羅","生","門","清","楚","淫","乱","妹",
                  "緑","単","相","撲","ア","イ","ウ","エ","オ","カ",
                  "キ","ク","ケ","コ","サ","シ","ス","セ","ソ","タ",
                  "チ","ツ","テ","ト","ナ","ニ","ヌ","ネ","ノ","ハ",
                  "ヒ","フ","屁","ホ","マ","ミ","ム","メ","モ","ヤ",
                  "ユ","ヨ","ラ","リ","ル","レ","ロ","ワ","ヲ","ン",
                  "外","星","人","激","怒","邪","智","暴","虐","芋",
                  "粥","作","業","枠","飲","酒","雑","談","甘","藍",
                  "ど","寝","前","過","呼","吸","更","配","信","者",
                  "達","質","問","箱","会","話","幻","塔","長","距",
                  "離","運","送","ー","ガ","ギ","グ","ゲ","ゴ","ザ",
                  "ジ","ズ","ゼ","ゾ","ダ","ヂ","ヅ","デ","ド","バ",
                  "美","ブ","ベ","ボ","パ","ピ","プ","ペ","ポ","肉",
                  "少","女","が","ぎ","ぐ","げ","ご","ざ","じ","ず",
                  "ぜ","ぞ","だ","ぢ","づ","で")

yuuhayashi=text
yuuhayashi=yuuhayashi.replace('ママでちゅよ', '右')
yuuhayashi=yuuhayashi.replace('有林', '左')
yuuhayashi=yuuhayashi.replace('おっぱい', '足')
yuuhayashi=yuuhayashi.replace('ボロン', '引')
yuuhayashi=yuuhayashi.replace('妹ちゃん', '出')
yuuhayashi=yuuhayashi.replace('護法2', '入')
yuuhayashi=yuuhayashi.replace('アピールしてください', '恥')
yuuhayashi=yuuhayashi.replace('こんもも', '終')


if on:
    if input=="":input="外星人かわいい"
    while cursol<=(len(yuuhayashi)-1):
        if yuuhayashi[cursol]=="右":
            workinghayashi=workinghayashi+1
            if workinghayashi==256:workinghayashi=0
            cursol=cursol+1
        elif yuuhayashi[cursol]=='左':
            workinghayashi=workinghayashi-1
            if workinghayashi==-1:workinghayashi=255
            cursol=cursol+1
        elif yuuhayashi[cursol]=='足':
            cells[workinghayashi]=cells[workinghayashi]+1
            if cells[workinghayashi]==256:cells[workinghayashi]=0
            cursol=cursol+1
        elif yuuhayashi[cursol]=='引':
            cells[workinghayashi]=cells[workinghayashi]-1
            if cells[workinghayashi]==-1:cells[workinghayashi]=255
            cursol=cursol+1
        elif yuuhayashi[cursol]=='出':
            output=output+aribayashiturple[cells[workinghayashi]]
            cursol=cursol+1
        elif yuuhayashi[cursol]=='入':
            for i in range(len(aribayashiturple)):
                if aribayashiturple[i]==input[nyuuryokubayashi]:
                    cells[workinghayashi]=i
                    break
            nyuuryokubayashi=nyuuryokubayashi+1
            if nyuuryokubayashi>len(input)-1:
                nyuuryokubayashi=len(input)-1
            cursol=cursol+1
        elif yuuhayashi[cursol]=='恥':
            if cells[workinghayashi]==0:
                tmpcount=1
                while tmpcount>0 and cursol<=(len(yuuhayashi)-1):
                    cursol=cursol+1
                    if yuuhayashi[cursol]=='恥':tmpcount=tmpcount+1
                    if yuuhayashi[cursol]=='終':tmpcount=tmpcount-1
                cursol=cursol+1
            else:
                cursol=cursol+1
        elif yuuhayashi[cursol]=='終':
            if cells[workinghayashi]==0:
                cursol=cursol+1
            else:
                cursol=cursol-1
                tmpcount=1
                while tmpcount>0 and cursol>=0:
                    cursol=cursol-1
                    if yuuhayashi[cursol]=='終':tmpcount=tmpcount+1
                    if yuuhayashi[cursol]=='恥':tmpcount=tmpcount-1
                cursol=cursol+1
                



    st.title("出力")
    st.write(output)
    time.sleep(300)
    cells=[0] * 256




`,
"data/logo.png": Ut("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"),
"pages/🎈_subpage.py": `import streamlit as st

st.title("Sub page")

st.markdown("""
_Stlite_ supports **Multi Page Apps (MPA)**, of course!

Create \`pages/*.py\` like this file to add new pages.

If you are new to MPA, read the official tutorial about it [🔗 here](https://docs.streamlit.io/library/get-started/multipage-apps)
""")
`,
"file1.py": ``,

},
  },
  document.getElementById("root")
)

function Ut(e){const t=window.atob(e),n=t.length,r=new Uint8Array(n);for(let a=0;a<n;a++)r[a]=t.charCodeAt(a);return r}
    </script>
  </body>
  <!-- Generated from stlite sharing (https://edit.share.stlite.net/), and the source version is 9605754c6cd12a2f17da6aee306239bb690dc81a -->
</html>
