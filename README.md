# Minecraft-sunucusu-chat-silme-kapatma-acma-skript
sunucuya ekstra plugin kurmadan chat silme kapatma açma eklemeniz içindir .
amacı basittir ekstra plugin kurmadan essentials in eklemedigi chat kapatma ve silmeyi ekler.
luckperms ile verebileceginiz izinler bulunur:
chat silme: chat.clear
chat kapatma-acma: chat.mute
chat kapaliyken yazma: chat.bypass
KURULUM
skript plugin kurup chat.sk dosyası acıp kodu icine yapıstırın ve oyunda /skript reload chat.sk yazınca komutlar gelir .

skript kodu alttadır dilerseniz ai ile düzenleyebilirsiniz kopyalayıp yapıstırabilirsiniz :

command /chatmute:
    permission: chat.mute
    trigger:
        if {chat.mute} is not true:
            set {chat.mute} to true
            broadcast "&csᴏʜʙᴇᴛ ᴋᴀᴘᴀᴛɪʟᴅɪ ! &f(&7%command sender%&f)"
        else:
            set {chat.mute} to false
            broadcast "&asᴏʜʙᴇᴛ ᴀᴄɪʟᴅɪ ! &f(&7%command sender%&f)"

on chat:
    if {chat.mute} is true:
        if player has permission "chat.bypass":
            stop
        cancel event
        send "&csᴏʜʙᴇᴛ sᴜ ᴀɴᴅᴀ ᴋᴀᴘᴀʟɪ !" to player

command /chatclear:
    permission: chat.clear
    trigger:
        loop all players:
            loop 100 times:
                send "" to loop-player
        broadcast "&esᴏʜʙᴇᴛ ᴛᴇᴍɪᴢʟᴇɴᴅɪ ! &f(&7%command sender%&f)"
