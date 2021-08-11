# folkis
Få notiser om lediga drop-in tider till Folktandvården i Stockholm.
Filerna placeras i /root/folkis eller annan mapp men då måste vissa ändringar göras.

Följ dessa sidor för att få till att skicka via Telegram
https://medium.com/@robertbracco1/how-to-write-a-telegram-bot-to-send-messages-with-python-bcdf45d0a580 eller
https://pypi.org/project/telegram-send/

För WhatsApp:
https://www.twilio.com/blog/send-whatsapp-message-30-seconds-python eller
https://www.twilio.com/docs/whatsapp/quickstart/python eller
https://www.youtube.com/watch?v=98OewpG8-yw <br>
sudo pip install twilio

Lägg till:<br> 
SHELL=/bin/bash <br>
i crontab.<br>

För att få kontroll var 15:e minut mellan 7-18 läggs detta till med crontab -e: <br> 
*/15 7-18 * * 1-5 /root/folkis/checkit

Och chekit innehåller i sin tur:<br>
cd /root/folkis<br>
python3.7 /root/folkis/folkis_final.py<br>
python3.7 /root/folkis/folkis_final2.py<br>

I /root/.bashrc läggs detta till utifrån vad du hittar i Twilios sandbox<br>
export TWILIO_ACCOUNT_SID="AC1dxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"<br>
export TWILIO_AUTH_TOKEN="ad8bxxxxxxxxxxxxxxxxxxxxxxxxxxxx"<br>
export from_whatsapp_number="whatsapp:+141xxxxxxxx"<br>
export to_whatsapp_number="whatsapp:+4670xxxxxxx"<br>
