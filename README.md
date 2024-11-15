import requests

# Ton token d'accès et ID du numéro WhatsApp Business
ACCESS_TOKEN = {
   "error": {
      "message": "Invalid OAuth 2.0 Access Token",
      "type": "WAApiException",
      "code": 190,
      "error_data": {
         
      },
      "fbtrace_id": "A_XxC4h9zabODV22XqVheBt"
   
PHONE_NUMBER_ID = "VOTRE_PHONE_NUMBER_ID"  # Trouvé dans la configuration de l'API
WHATSAPP_API_URL = f"https://graph.whatsapp.com/v16.0/{PHONE_NUMBER_ID}/messages"

# Fonction pour envoyer un message
def envoyer_message(to, message):
    headers = {
        "Authorization": f"Bearer {ACCESS_TOKEN}",
        "Content-Type": "application/json"
    }acces watsapp
    data = {
        "messaging_product": "whatsapp",
        "to": to,bodiaely
        "type": "text",
        "text": {"body": message}
    }
    response = requests.post(WHATSAPP_API_URL, headers=headers, json=data)
    if response.status_code == 200:
        print("Message envoyé avec succès !")
    else:
        print(f"Erreur : {response.status_code}, {response.text}")

# Exemple d'utilisation
if __name__ == "__main__":
    numero_24104245289gabon
    message = "Salut ! C'est un bot WhatsApp."
    envoyer_message(numero_test, message)python whatsapp_bot.py