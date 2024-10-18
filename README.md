- 👋 Hi, I’m @Elybodia
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...



👋 Hello ⟭𖣐⟬𝕿𝖍𝖊 𝖆𝖓𝖌𝖊𝖑 𝖉𝖎𝖛𝖎𝖓𝖊 𝖉𝖔𝖒𝖎𝖓𝖚𝖘𖢖👋
//base by elybidia 
//re-upload? recode? copy code? give credit ya :)
//YouTube: @elybodia
//Instagram: its_elybodia
//Telegram: t.me/elybodia10
//GitHub: @elybodia
//WhatsApp: +24174245289
//want more free bot scripts? subscribe to my youtube channel: https://youtube.com/@elybodia


const {
   spawn
} = require('child_process')
const path = require('path')

function start() {
   let args = [path.join(__dirname, 'main.js'), ...process.argv.slice(2)]
   console.log([process.argv[0], ...args].join('\n'))
   let p = spawn(process.argv[0], args, {
         stdio: ['inherit', 'inherit', 'inherit', 'ipc']
      })
      .on('message', data => {
         if (data == 'reset') {
            console.log('Restarting Bot...')
            p.kill()
            start()
            delete p
         }
      })
      .on('exit', code => {
         console.error('Exited with code:', code)
         if (code == '.' || code == 1 || code == 0) start()
      })
}
start()
