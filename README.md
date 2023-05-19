#!/usr/bin/python

# This is a simple echo bot using the decorator mechanism.
# It echoes any incoming text messages.

import telebot

API_TOKEN = '5974597380:AAERuBGaL874zauYaNQXlbP2euBpNlDa8gU'

bot = telebot.TeleBot(API_TOKEN)


# Handle '/start' and '/help'
@bot.message_handler(commands=['help', 'start'])
def send_welcome(message):
    bot.reply_to(message, """\
Ciao questo è il primo bot dedicato agli affitti sull 'isola di la Maddalena .
Inviaci  o inserisci richieste del tuo , o vostri immobili ,preventivi immediati e gratuiti\
""")


# Handle all other messages with content_type 'text' (content_types defaults to ['text'])
@bot.message_handler(func=lambda message: True)
def echo_message(message):
if message.text=='Ciao':
    bot.reply_to(message,'Ciao io sono il primo bot dedicato agli affitti sull 'isola di la Maddalena cell 3711615257')





bot.infinity_polling()
