# Secret-Story
Secret Story
<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Inscription - Secret Story</title>
  <style>
    /* Reset & base */
    :root{
      --bg:#080814;
      --card:#0f1220;
      --accent:#ff2d95;
      --accent-2:#6af0ff;
      --muted:#bfc6d1;
      --glass: rgba(255,255,255,0.04);
      --radius:14px;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:radial-gradient(circle at 10% 10%, rgba(106,240,255,0.05), transparent 10%), linear-gradient(180deg,#05050a 0%, #0b0b12 100%);color:var(--muted);}
    a{color:var(--accent-2)}

    /* Layout */
    .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:40px}
    .card{width:100%;max-width:980px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:var(--radius);padding:28px;box-shadow:0 10px 30px rgba(2,6,23,0.6);border:1px solid rgba(255,255,255,0.03);display:grid;grid-template-columns:1fr 420px;gap:24px}

    /* Left column: form */
    .hero{padding:8px 6px}
    .kicker{display:inline-block;background:linear-gradient(90deg,var(--accent),var(--accent-2));-webkit-background-clip:text;background-clip:text;color:transparent;font-weight:700}
    h1{margin:6px 0 12px;color:white;font-size:22px}
    p.lead{margin:0 0 18px;color:var(--muted);line-height:1.4}

    form{display:grid;gap:12px}
    .row{display:flex;gap:12px}
    .col{flex:1}
    label{display:block;font-size:13px;color:#9aa3b2;margin-bottom:6px}
    input[type="text"],input[type="email"],input[type="tel"],input[type="date"],textarea,select{
      width:100%;padding:10px 12px;border-radius:10px;background:var(--glass);border:1px solid rgba(255,255,255,0.04);color:var(--muted);outline:none;font-size:14px}
    textarea{min-height:110px;resize:vertical}

    .filezone{display:flex;align-items:center;justify-content:center;flex-direction:column;padding:12px;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));border:1px dashed rgba(255,255,255,0.03);min-height:96px;}
    .small{font-size:12px;color:#8b94a0}

    .actions{display:flex;gap:12px;align-items:center;margin-top:6px}
    .btn{padding:10px 14px;border-radius:10px;border:0;font-weight:700;cursor:pointer}
    .btn-primary{background:linear-gradient(90deg,var(--accent),#ff7bbd);color:white;box-shadow:0 6px 18px rgba(255,45,149,0.12)}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.05);color:var(--muted)}

    /* Right column: info */
    .aside{padding:18px;border-radius:10px;background:linear-gradient(180deg, rgba(10,12,22,0.6), rgba(12,14,26,0.4));}
    .aside h3{color:white;margin-top:0}
    .meta{font-size:13px;line-height:1.5}
    .badge{display:inline-block;padding:6px 10px;border-radius:999px;font-weight:700;background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.03);color:var(--muted);margin-right:8px}

    /* confirmation */
    .notice{padding:12px;border-radius:8px;background:rgba(106,240,255,0.06);border:1px solid rgba(106,240,255,0.08);color:var(--accent-2)}

    /* responsive */
    @media (max-width:880px){.card{grid-template-columns:1fr;max-width:720px}.aside{order:2}}
    @media (max-width:520px){.row{flex-direction:column}}

    /* little neon accent */
    .logo{display:inline-flex;align-items:center;gap:10px}
    .logo .dot{width:12px;height:12px;border-radius:50%;background:var(--accent);box-shadow:0 6px 20px rgba(255,45,149,0.25)}

    /* helper text */
    .error{color:#ff8b8b;font-size:13px}
  </style>
</head>
<body>
  <div class="wrap">
    <div class="card">
      <div class="hero">
        <div class="logo"><span class="dot"></span><strong style="color:white">Secret Story</strong></div>
        <div style="height:8px"></div>
        <span class="kicker">Casting</span>
        <h1>Inscris-toi au casting — Secret Story</h1>
        <p class="lead">Remplis le formulaire ci-dessous pour postuler. Les vidéos et photos sont fortement recommandées pour augmenter tes chances.</p>

        <form id="applyForm" novalidate>
          <div class="row">
            <div class="col">
              <label for="firstname">Prénom</label>
              <input id="firstname" name="firstname" type="text" required placeholder="Ton prénom" />
            </div>
            <div class="col">
              <label for="lastname">Nom</label>
              <input id="lastname" name="lastname" type="text" required placeholder="Ton nom" />
            </div>
          </div>

          <div class="row">
            <div class="col">
              <label for="birth">Date de naissance</label>
              <input id="birth" name="birth" type="date" required />
            </div>
            <div class="col">
              <label for="phone">Téléphone</label>
              <input id="phone" name="phone" type="tel" placeholder="+225 07 xx xx xx" />
            </div>
          </div>

          <label for="email">Email</label>
          <input id="email" name="email" type="email" required placeholder="exemple@mail.com" />

          <label for="city">Ville / Pays</label>
          <input id="city" name="city" type="text" placeholder="Abidjan, Côte d'Ivoire" />

          <label for="pitch">Présentation rapide (1-2 phrases)</label>
          <textarea id="pitch" name="pitch" placeholder="Parle-nous de toi en quelques mots..."></textarea>

          <label for="why">Pourquoi veux-tu participer ?</label>
          <textarea id="why" name="why" placeholder="Explique tes motivations"></textarea>

          <label for="secret">Ton secret (facultatif)</label>
          <input id="secret" name="secret" type="text" placeholder="Si tu veux le partager pour le casting" />

          <div style="display:flex;gap:12px;margin-top:4px;flex-wrap:wrap">
            <div style="flex:1">
              <label>Photo de profil (jpg/png)</label>
              <div class="filezone" id="photoZone">
                <input type="file" id="photo" accept="image/*" style="display:none" />
                <button type="button" class="btn btn-ghost" onclick="document.getElementById('photo').click()">Choisir une photo</button>
                <div class="small">Max 5 Mo</div>
                <div id="photoPreview" style="margin-top:8px"></div>
              </div>
            </div>

            <div style="flex:1">
              <label>Vidéo de présentation (mp4) — facultatif</label>
              <div class="filezone" id="videoZone">
                <input type="file" id="video" accept="video/*" style="display:none" />
                <button type="button" class="btn btn-ghost" onclick="document.getElementById('video').click()">Importer une vidéo</button>
                <div class="small">Max 50 Mo — 60s max recommandé</div>
                <div id="videoPreview" style="margin-top:8px"></div>
              </div>
            </div>

            <div style="flex-basis:100%"></div>

            <div style="flex:1">
              <label>Pièce d'identité (optionnel)</label>
              <div class="filezone">
                <input type="file" id="idfile" accept="image/*,application/pdf" style="display:none" />
                <button type="button" class="btn btn-ghost" onclick="document.getElementById('idfile').click()">Téléverser</button>
                <div class="small">Utilisé seulement pour vérification si nécessaire</div>
              </div>
            </div>
          </div>

          <div style="display:flex;align-items:center;gap:8px;margin-top:8px">
            <input id="terms" type="checkbox" required />
            <label for="terms" style="font-size:13px;color:#9aa3b2">J'accepte les <a href="#">conditions de participation</a> et la <a href="#">politique de confidentialité</a>.</label>
          </div>

          <div class="actions">
            <button type="submit" class="btn btn-primary">Valider mon inscription</button>
            <button type="reset" class="btn btn-ghost">Réinitialiser</button>
            <div id="formMsg" style="margin-left:auto"></div>
          </div>

          <div id="errors" class="error" aria-live="polite"></div>
        </form>
      </div>

      <aside class="aside">
        <h3>Infos casting</h3>
        <p class="meta">Dates du casting : <strong>à préciser</strong><br/>Age minimum : <strong>18 ans</strong><br/>Durée de la réponse : <strong>2–6 semaines</strong></p>
        <div style="height:12px"></div>
        <div class="badge">Confidentiel</div>
        <p style="margin-top:12px">Ton secret restera confidentiel dans le processus de sélection. Les fichiers sont stockés de manière sécurisée côté serveur (si tu déploies le site).</p>
        <div style="height:12px"></div>
        <div class="notice">Astuce : une vidéo claire (60s) et une photo expressive augmentent tes chances.</div>
      </aside>
    </div>
  </div>

  <script>
    // small client-side helpers: preview and minimal validation
    const photo = document.getElementById('photo');
    const photoPreview = document.getElementById('photoPreview');
    const video = document.getElementById('video');
    const videoPreview = document.getElementById('videoPreview');
    const form = document.getElementById('applyForm');
    const errors = document.getElementById('errors');
    const formMsg = document.getElementById('formMsg');

    photo.addEventListener('change', e => {
      const f = e.target.files[0];
      photoPreview.innerHTML = '';
      if(!f) return;
      if(f.size > 5 * 1024 * 1024){ photoPreview.innerText = 'Fichier trop volumineux (max 5 Mo)'; return; }
      const img = document.createElement('img'); img.style.maxWidth='120px'; img.style.borderRadius='8px'; img.src = URL.createObjectURL(f);
      photoPreview.appendChild(img);
    });

    video.addEventListener('change', e => {
      const f = e.target.files[0];
      videoPreview.innerHTML = '';
      if(!f) return;
      if(f.size > 50 * 1024 * 1024){ videoPreview.innerText = 'Fichier trop volumineux (max 50 Mo)'; return; }
      const vid = document.createElement('video'); vid.controls=true; vid.style.maxWidth='180px'; vid.src = URL.createObjectURL(f);
      videoPreview.appendChild(vid);
    });

    form.addEventListener('submit', e => {
      e.preventDefault();
      errors.innerText=''; formMsg.innerText='';
      // minimal validation
      const required = ['firstname','lastname','birth','email','terms'];
      const missing = [];
      required.forEach(id => {
        const el = document.getElementById(id);
        if(el){
          if((el.type === 'checkbox' && !el.checked) || (!el.value && el.type !== 'checkbox')) missing.push(id);
        }
      });
      if(missing.length){ errors.innerText = 'Veuillez remplir tous les champs requis.'; return; }

      // build a small preview object (client-side). In real life, submit to backend.
      const data = new FormData(form);
      // show a friendly confirmation (simulate server response)
      formMsg.innerText = '✔️ Candidature envoyée';
      formMsg.style.color = 'var(--accent-2)';
      // show reference
      const ref = 'SS-' + Date.now().toString().slice(-6);
      alert('Merci ! Votre candidature a bien été enregistrée. Référence: ' + ref);
      form.reset(); photoPreview.innerHTML=''; videoPreview.innerHTML='';
    });
  </script>
</body>
</html>
