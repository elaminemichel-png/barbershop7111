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
