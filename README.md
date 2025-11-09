# pogect
tg bot
import telebot   
bot = telebot.TeleBot("")    
@bot.message_handler(commands=['start'])
def send_welcome(message):
    bot.reply_to(message, "Привет! выбери команду!")   
@bot.message_handler(commands=['hello'])
def send_hello(message):
    bot.reply_to(message, "Привет!")  
@bot.message_handler(commands=['bye'])
def send_bye(message):
    bot.reply_to(message, "Пока! Увидимся!")   
@bot.message_handler(func=lambda message: True)
def echo_all(message):
    bot.reply_to(message, message.text)
@bot.message_handler(commands=['mem'])
def send_mem(message):
    with open('images/mem1.jpg', 'rb') as f:  
        bot.send_photo(message.chat.id, f)
bot.infinity_polling()
