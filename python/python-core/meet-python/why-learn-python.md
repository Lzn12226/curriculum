import logging
import telebot

# Configuração do token do bot
TOKEN = '6527933700:AAHHQKqiN4G2rWdOv2ts_msWqBGeCDB4g6w'

# Configuração do logger
logging.basicConfig(format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', level=logging.INFO)

# Crie um objeto Bot
bot = telebot.TeleBot(TOKEN)

# Função para lidar com o comando /start
@bot.message_handler(commands=['start'])
def start(message):
    user = message.from_user
    bot.send_message(message.chat.id, f'Olá, {user.first_name}! Bem-vindo ao nosso grupo.')

# Função para lidar com mensagens recebidas
@bot.message_handler(func=lambda message: True)
def echo(message):
    bot.send_message(message.chat.id, message.text)

def main():
    # Inicie o bot
    bot.polling()

if __name__ == '__main__':
    main()
    - `"That's the spirit! 🎉"`
