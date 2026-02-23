<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modestine · carte de présentation</title>
  <style>
    /* === RESET & POLICES === */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #d4dde1 0%, #b7c4cc 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Segoe UI', Roboto, system-ui, -apple-system, sans-serif;
      padding: 1.5rem;
    }

    /* === CARTE PRINCIPALE (style CV / fiche élégante) === */
    .carte {
      max-width: 860px;
      width: 100%;
      background: #fcf9f4;  /* blanc cassé doux */
      border-radius: 2.5rem 2.5rem 2rem 2rem;
      box-shadow: 0 25px 40px -10px rgba(20, 30, 40, 0.35),
                  0 10px 20px -5px rgba(0, 0, 0, 0.15);
      overflow: hidden;
      transition: all 0.2s ease;
      border: 1px solid rgba(255, 255, 255, 0.5);
      backdrop-filter: blur(2px);
    }

    /* bande supérieure ornementale */
    .carte-header {
      background: #1f3a4b;  /* bleu‑vert profond */
      padding: 2rem 2rem 1.5rem 2rem;
      color: white;
      border-bottom: 4px solid #e2b868;
    }

    .carte-header h1 {
      font-size: 2.2rem;
      font-weight: 600;
      letter-spacing: 1px;
      line-height: 1.2;
    }

    .carte-header h1 small {
      display: block;
      font-size: 1.1rem;
      font-weight: 400;
      opacity: 0.85;
      margin-top: 0.4rem;
      text-transform: uppercase;
      letter-spacing: 2px;
      word-spacing: 4px;
    }

    /* grille principale : identité + infos perso */
    .grid-identite {
      display: flex;
      flex-wrap: wrap;
      background: #f5efe8;
      padding: 1.8rem 2rem;
      gap: 2rem;
      border-bottom: 1px solid #ded3c7;
    }

    .bloc-nom {
      flex: 2 1 260px;
    }

    .bloc-nom p {
      margin: 0.5rem 0;
      font-size: 1.15rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      color: #1f3a4b;
    }

    .bloc-nom i { 
      font-style: normal; 
      font-size: 1.3rem; 
      min-width: 1.8rem;
      color: #e2b868;
      text-shadow: 0 1px 1px #bba16b;
    }

    .bloc-telecom {
      flex: 1 1 220px;
      background: rgba(226, 184, 104, 0.12);
      padding: 1rem 1.5rem;
      border-radius: 2rem 1rem 1rem 2rem;
      border-left: 3px solid #e2b868;
    }

    .bloc-telecom p {
      margin: 0.55rem 0;
      font-size: 1rem;
      display: flex;
      align-items: center;
      gap: 0.7rem;
      color: #1f3a4b;
      word-break: break-word;
    }

    .bloc-telecom i {
      font-style: normal;
      font-weight: 600;
      color: #1f3a4b;
      background: #e2b868;
      width: 28px;
      height: 28px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      font-size: 1rem;
    }

    /* séparateur discret */
    .separateur {
      height: 1px;
      background: linear-gradient(90deg, transparent, #cbb59b, transparent);
      margin: 0 2rem;
    }

    /* sections communes (formation, langues, expérience) */
    .contenu-carte {
      padding: 1.8rem 2rem 2.2rem 2rem;
    }

    .rubrique {
      margin-bottom: 2.2rem;
    }

    .rubrique:last-child {
      margin-bottom: 0;
    }

    .rubrique h2 {
      font-size: 1.7rem;
      font-weight: 500;
      color: #1f3a4b;
      border-bottom: 2px dashed #e2b868;
      padding-bottom: 0.4rem;
      margin-bottom: 1.3rem;
      letter-spacing: -0.5px;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .rubrique h2 span {
      background: #e2b868;
      color: #1f3a4b;
      font-size: 1.2rem;
      width: 36px;
      height: 36px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
    }

    /* listes formation */
    .formation-liste {
      list-style: none;
    }

    .formation-item {
      display: flex;
      flex-wrap: wrap;
      align-items: baseline;
      gap: 0.8rem;
      padding: 0.5rem 0 0.5rem 1rem;
      border-left: 3px solid transparent;
      transition: 0.1s ease;
      font-size: 1.1rem;
    }

    .formation-item:hover {
      border-left-color: #e2b868;
      background: rgba(226, 184, 104, 0.05);
    }

    .formation-annee {
      font-weight: 600;
      background: #e8dfd3;
      padding: 0.15rem 1rem;
      border-radius: 30px;
      color: #1f3a4b;
      font-size: 0.9rem;
      letter-spacing: 0.3px;
      min-width: 100px;
      text-align: center;
    }

    .formation-detail {
      font-weight: 500;
      color: #2c3e4f;
    }

    /* compétences linguistiques & informatique */
    .competences-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1.8rem;
      margin-top: 0.5rem;
    }

    .langues, .info {
      flex: 1 1 200px;
    }

    .langues h3, .info h3 {
      font-size: 1.3rem;
      font-weight: 500;
      margin-bottom: 0.8rem;
      color: #314e60;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .badge-langue {
      display: inline-block;
      background: #1f3a4b;
      color: white;
      padding: 0.35rem 1.2rem;
      border-radius: 40px;
      font-size: 1rem;
      margin: 0.25rem 0.25rem 0.25rem 0;
      box-shadow: 0 4px 6px rgba(0,0,0,0.03);
    }

    .badge-langue span {
      font-weight: 300;
      opacity: 0.9;
      margin-left: 0.4rem;
      background: #e2b868;
      color: #1f3a4b;
      padding: 0.1rem 0.6rem;
      border-radius: 30px;
      font-size: 0.8rem;
    }

    .info-puce {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      margin: 0.6rem 0;
      font-size: 1.1rem;
      background: #ecf0f3;
      padding: 0.3rem 1rem 0.3rem 0.8rem;
      border-radius: 40px;
      width: fit-content;
    }

    .info-puce code {
      background: #1f3a4b;
      color: #e2b868;
      padding: 0.2rem 0.9rem;
      border-radius: 40px;
      font-size: 0.9rem;
      font-family: 'Fira Code', monospace;
    }

    /* petit accent */
    .detail-note {
      margin-top: 1.2rem;
      font-style: italic;
      color: #4d5f69;
      border-top: 1px dotted #c5b4a2;
      padding-top: 0.8rem;
      font-size: 0.95rem;
      display: flex;
      gap: 0.5rem;
      align-items: center;
    }

    .detail-note strong {
      color: #1f3a4b;
      font-weight: 600;
    }

    /* mobile */
    @media (max-width: 520px) {
      .carte-header h1 { font-size: 1.7rem; }
      .grid-identite { padding: 1.2rem; gap: 1rem; }
      .bloc-telecom { padding: 0.8rem; }
      .formation-item { flex-direction: column; align-items: flex-start; gap: 0.2rem; }
      .formation-annee { min-width: auto; }
    }

    /* impression très propre */
    @media print {
      body { background: white; padding: 0.2in; }
      .carte { box-shadow: none; border: 1px solid #aaa; max-width: 100%; }
    }

    /* pictos simples (remplacent fontawesome) */
    .picto { font-size: 1.3rem; line-height: 1; }
  </style>
</head>
<body>
  <div class="carte">
    <!-- bandeau supérieur avec nom/prénom -->
    <div class="carte-header">
      <h1>
        Razafiniaina
        <small>Valimbavaka Modestine</small>
      </h1>
    </div>

    <!-- coordonnées : adresse, téléphone, email -->
    <div class="grid-identite">
      <div class="bloc-nom">
        <p><i class="picto">🏠</i> Adresse : Ambatoharanana Andrainjato</p>
        <p><i class="picto">📞</i> Téléphone : 038 33 47 445</p>
        <p><i class="picto">✉️</i> valimbavakamodestine@gmail.com</p>
      </div>
      <div class="bloc-telecom">
        <p><i>📬</i> Ambatoharanana</p>
        <p><i>📱</i> 038 33 47 445</p>
        <p><i>@</i> gmail • modestine</p>
      </div>
    </div>

    <div class="separateur"></div>

    <!-- corps détaillé -->
    <div class="contenu-carte">
      <!-- FORMATION ACADÉMIQUE -->
      <section class="rubrique">
        <h2>
          <span>🎓</span> Formation académique
        </h2>
        <ul class="formation-liste">
          <li class="formation-item">
            <span class="formation-annee">2024-2025</span>
            <span class="formation-detail">Baccalauréat (BACC)</span>
          </li>
          <li class="formation-item">
            <span class="formation-annee">2021-2022</span>
            <span class="formation-detail">BEPC</span>
          </li>
          <li class="formation-item">
            <span class="formation-annee">2017-2018</span>
            <span class="formation-detail">CEPE</span>
          </li>
          <li class="formation-item" style="margin-top: 0.6rem;">
            <span class="formation-annee">Première année</span>
            <span class="formation-detail">Licence DA2I (en cours)</span>
          </li>
        </ul>
      </section>

      <!-- COMPÉTENCES LINGUISTIQUES ET EXPÉRIENCE INFORMATIQUE -->
      <section class="rubrique">
        <h2>
          <span>💬</span> Langues & informatique
        </h2>
        <div class="competences-grid">
          <!-- langues -->
          <div class="langues">
            <h3>🌐 Compétence linguistique</h3>
            <div>
              <span class="badge-langue">Français <span>assez bien</span></span>
              <span class="badge-langue">Anglais <span>intermédiaire</span></span>
            </div>
            <!-- petite note additionnelle -->
            <div style="margin-top: 0.8rem; color: #314e60; font-size: 0.95rem;">
              ✔ Compréhension et expression orale
            </div>
          </div>

          <!-- expérience en informatique -->
          <div class="info">
            <h3>💻 Expérience en informatique</h3>
            <div class="info-puce">
              <code>HTML</code> <span style="color:#1f3a4b;">structure sémantique</span>
            </div>
            <div class="info-puce">
              <code>CSS</code> <span style="color:#1f3a4b;"> mise en page, flex, grid</span>
            </div>
            <div class="detail-note">
              <span>🖥️</span> <strong>DA2I (1ʳᵉ année)</strong> — bases du développement web
            </div>
          </div>
        </div>
      </section>

      <!-- Petit rappel des infos personnelles (élégant) -->
      <section class="rubrique" style="margin-bottom: 0;">
        <h2 style="border-bottom-style: solid; border-bottom-width: 1px;">
          <span>📌</span> Fiche contact
        </h2>
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 0.7rem; font-size: 1.05rem;">
          <span><strong>Nom complet :</strong> RAZAFINIAINA Valimbavaka Modestine</span>
          <span><strong>Ville :</strong> Ambatoharanana Andrainjato</span>
          <span><strong>Tél :</strong> 038 33 47 445</span>
        </div>
        <div style="margin-top: 1rem; background: #e2b86820; padding: 0.7rem 1rem; border-radius: 50px; text-align: center; color: #1f3a4b;">
          📧 valimbavakamodestine@gmail.com
        </div>
      </section>
    </div>
    <!-- petit footer léger -->
    <div style="background: #e2b868; height: 5px; width: 100%;"></div>
  </div>
</body>
</html>
