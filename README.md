import requests

# Ton token d'accès et ID du numéro WhatsApp Business
ACCESS_TOKEN = "VOTRE_TOKEN_D'ACCÈS"
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