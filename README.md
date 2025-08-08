<section id="rendezvous-section" class="card" style="margin-top:20px;">
  <h2>Prise de rendez-vous</h2>
  <form id="rdv-form">
    <label>Nom du client :</label><br />
    <input type="text" id="client-name" required /><br /><br />
    
    <label>Choisir un coiffeur :</label><br />
    <select id="coiffeur-select" required>
      <option value="">-- Sélectionnez --</option>
      <option value="El-Amine">El-Amine</option>
      <option value="Sanad">Sanad</option>
      <option value="Karima">Karima</option>
    </select><br /><br />
    
    <label>Date et heure :</label><br />
    <input type="datetime-local" id="rdv-date" required /><br /><br />
    
    <button type="submit" class="btn">Réserver</button>
  </form>
  <div id="rdv-message" style="margin-top:10px;"></div>
  
  <h3>Rendez-vous prévus</h3>
  <ul id="rdv-list"></ul>
</section>
// Gestion des rendez-vous
const rdvForm = document.getElementById('rdv-form');
const rdvMessage = document.getElementById('rdv-message');
const rdvList = document.getElementById('rdv-list');

// Stockage simple en mémoire (tu pourras plus tard connecter à une BDD)
const rendezvous = [];

rdvForm.addEventListener('submit', function(e) {
  e.preventDefault();
  
  const clientName = document.getElementById('client-name').value.trim();
  const coiffeur = document.getElementById('coiffeur-select').value;
  const date = document.getElementById('rdv-date').value;
  
  if (!clientName || !coiffeur || !date) {
    rdvMessage.textContent = 'Veuillez remplir tous les champs.';
    rdvMessage.style.color = 'red';
    return;
  }
  
  const newRdv = { clientName, coiffeur, date };
  rendezvous.push(newRdv);
  
  rdvMessage.textContent = `Rendez-vous pris pour ${clientName} avec ${coiffeur} le ${new Date(date).toLocaleString()}`;
  rdvMessage.style.color = 'green';
  
  rdvForm.reset();
  afficherRendezvous();
});

function afficherRendezvous() {
  rdvList.innerHTML = '';
  if (rendezvous.length === 0) {
    rdvList.textContent = 'Aucun rendez-vous prévu.';
    return;<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Barbershop 7eleven</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f6f6f6;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #b40000;
      color: white;
      padding: 20px;
      text-align: center;
    }
    h1 {
      margin: 0;
    }
    .container {
      max-width: 900px;
      margin: 20px auto;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 6px 18px rgba(0,0,0,0.1);
    }
    #rendezvous-section input,
    #rendezvous-section select {
      width: 100%;
      padding: 8px;
      margin-top: 4px;
      border-radius:

  }
  rendezvous.forEach((rdv, i) => {
    const li = document.createElement('li');
    li.textContent = `${rdv.clientName} - ${rdv.coiffeur} - ${new Date(rdv.date).toLocaleString()}`;
    rdvList.appendChild(li);
  });
}

// Appelle l'affichage au chargement
afficherRendezvous();
