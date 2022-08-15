
<p align="center">
   <img src="https://img.shields.io/npm/dt/niby-welcomes?style=for-the-badge">
   <img src="https://img.shields.io/github/stars/justdiegocom/niby-welcomes.svg?style=for-the-badge">
   <img src="https://img.shields.io/github/issues/justdiegocom/niby-welcomes.svg?style=for-the-badge">
   <img src="https://img.shields.io/npm/v/niby-welcomes?style=for-the-badge">
   <img src="https://img.shields.io/github/license/justdiegocom/niby-welcomes.svg?style=for-the-badge">
</p>   



  <p align="center">
    <strong> Dar la bienvenida a un usuario nunca había sido tan fácil <br> <a href="https://nibywelcomes.netlify.app/"> Niby Welcomes </a></strong>
    <br />
    <a href="https://nibywelcomes.netlify.app/"><strong>Revisar documentación »</strong></a>
    <br />
    <br />
    <a href="https://nibywelcomes.netlify.app/">Documentación</a>
    ·
    <a href="https://discord.gg/MBPsvcphGf">Discord</a>
  </p>
</p>


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Índice de Contenido</summary>
  <ol>
    <li>
      <a href="#features">Características</a>
      <ul>
      </ul>
    </li>
    <li>
     <a href="#installation">Instalación</a>
    </li>
    <li><a href="#usage">Uso</a></li>
    <li><a href="#contributing">Contribución</a></li>
    <li><a href="#contact">Contacto</a></li>
    <li><a href="#credits">Soporte</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
# Características

* 😎 Distintos modos de bienvenida 
* 🚀 Generación de imagen súper rápida
* 🔥 Distintos estilos de bienvenidas
* ✅ Super fácil de utilizar


# Instalación

Instala el paquete con el siguiente comando en tu terminal:

```JS
npm i niby-welcomes
```

<!-- EJEMPLOS DE USO -->
## Uso
### Imagen de Bienvenida
```JS
const {Welcomes, Leaves} = require("niby-welcomes")
const Discord = require("discord.js")

module.exports = client => {

  client.on("guildMemberAdd", async member => {
    let myWelcomeDB = await db.findOne({guildID: member.guild.id});

    let welcomeChannel = member.guild.channels.cache.get(myWelcomeDB.channel);

    if(welcomeChannel){ 
      //CREACIÓN DE BUFFER DE IMAGEN (BIENVENIDA)
      let welcomeImage = await new Welcome()
      .setWelcomeMessage("BIENVENID@")
      .setUsername(member.user.username, /*OPCIONAL*/ {color: "#ffffff"})
      .setMemberCount(`Eres el número #${member.guild.memberCount}`, /*OPCIONAL*/ {color: "#ffffff"})
      .setAvatar(avatarUrl)
      .setBackgroundUrl(backgroundUrl, /*OPCIONAL*/ {opacity: backgroundOpacity})
      .setBorder(true, /*OPCIONAL*/ {color: borderColor, size: borderSize})
      .setStyle("koya") //koya, mee6
      .build();
    }

    //attachment
    let attachment = new Discord.AttachmentBuilder(welcomeImage, {name: `bienvenida-${member.user.tag}.png`})

    //enviamos el mensaje con la bienvenida
    welcomeChannel.send({content: `Bienvenido ${member.user} a ${member.guild.name}!`, files: [attachment]})
  })
}


```
## Resultado
![Bienvenida](https://i.ibb.co/Wv5WWvH/koya-justdiegocom-1088.png)
_Para más ejemplos, revisa la [Documentación](https://nibywelcomes.netlify.app/)_


<!-- CONTRIBUTING -->
## Contribución

Las contribuciones son lo que hace que la comunidad de código abierto sea un lugar increíble para aprender, inspirar y crear. Cualquier contribución que hagas es **muy apreciada**.

1. Crea un fork del proyecto
2. Crea una rama de tu característica (`git checkout -b feature/SuperCaracterística`)
3. Haz un commit de tus cambios (`git commit -m 'Adición de una SuperCaracterística'`)
4. Haz un push de la rama (`git push origin feature/SuperCaracterística`)
5. Abre un Pull Request

<!-- CONTACT -->
## Contacto

justdiegocom - 

Link del Proyecto: https://github.com/justdiegocom/niby-welcomes



<!-- Soporte -->
## Soporte
* [El Mundo de Niby](https://discord.gg/MBPsvcphGf)
* [Discord de Soporte](https://discord.gg/MBPsvcphGf)