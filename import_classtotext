import requests
from bs4 import BeautifulSoup

def get_text_by_class(url, class_name):
    # Faire la requête GET pour récupérer le contenu HTML de la page
    response = requests.get(url)
    
    # Vérifier si la requête a réussi
    if response.status_code == 200:
        # Analyser le HTML avec BeautifulSoup
        soup = BeautifulSoup(response.text, 'html.parser')
        
        # Trouver tous les éléments avec la classe spécifiée
        elements = soup.find_all(class_=class_name)
        
        # Récupérer le texte de chaque élément et l'ajouter à une liste
        element_texts = [element.get_text() for element in elements]
        
        return element_texts
    else:
        # Si la requête a échoué, afficher un message d'erreur
        print("La requête a échoué. Statut de la réponse :", response.status_code)
        return None

# URL du site à partir duquel vous souhaitez récupérer les éléments
url = "https://www.URLAREMPLIRICI.com/"
# Classe des éléments que vous souhaitez récupérer
class_name = "CLASSAMETTREICI"

# Appel de la fonction pour récupérer les éléments par classe
texts = get_text_by_class(url, class_name)

# Afficher les éléments récupérés
if texts:
    print("Texte des éléments avec la classe", class_name, "sur", url, ":")
    for text in texts:
        print(text)
else:
    print("Impossible de récupérer les éléments avec la classe", class_name, "depuis", url)
