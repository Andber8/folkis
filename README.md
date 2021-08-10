# folkis
Få notiser om lediga drop-in tider till Folktandvården i Stockholm.
Filerna placeras i /root/folkis eller annan mapp

Följ dessa sidor för att få till att skicka via Telegram
https://medium.com/@robertbracco1/how-to-write-a-telegram-bot-to-send-messages-with-python-bcdf45d0a580
https://pypi.org/project/telegram-send/

För WhatsApp:
https://www.twilio.com/docs/whatsapp/quickstart/python
https://www.youtube.com/watch?v=98OewpG8-yw
sudo pip install twilio

Lägg till 
SHELL=/bin/bash
i crontab.

För att få kontroll var 15:e minut mellan 7-18 läggs detta till:
*/15 7-18 * * 1-5 /root/folkis/checkit

Och chekit innehåller i sin tur:
cd /root/folkis
python3.7 /root/folkis/folkis_final.py
python3.7 /root/folkis/folkis_final2.py

I /root/.bashrc läggs detta till utifrån vad du hittar i Twilios sandbox
export TWILIO_ACCOUNT_SID="AC1dxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
export TWILIO_AUTH_TOKEN="ad8bxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
export from_whatsapp_number="whatsapp:+141xxxxxxxx"
export to_whatsapp_number="whatsapp:+4670xxxxxxx"
