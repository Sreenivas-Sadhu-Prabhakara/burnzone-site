---
title: Feedback
hide:
  - toc
---

# Share your feedback

Tried BurnZone? Tell us how it went — it all lands in one place for the team. Only the
comments or a rating are required; everything else is optional.

<form id="bz-feedback" class="bz-form" autocomplete="off">
  <div class="bz-form__row">
    <label>I tested as
      <select name="persona">
        <option value="">— choose —</option>
        <option value="member">Member</option>
        <option value="branch_admin">Branch Admin</option>
        <option value="trainer">Trainer</option>
        <option value="super_admin">Super Admin</option>
        <option value="other">Other</option>
      </select>
    </label>
    <label>App
      <select name="app">
        <option value="">— choose —</option>
        <option value="member">Member app</option>
        <option value="admin">Admin console</option>
        <option value="site">This site</option>
        <option value="other">Other</option>
      </select>
    </label>
    <label>Area / screen
      <input type="text" name="area" maxlength="100" placeholder="e.g. Book, Dashboard, Sign-in">
    </label>
  </div>

  <div class="bz-form__row">
    <fieldset class="bz-rating">
      <legend>Overall rating</legend>
      <label><input type="radio" name="rating" value="1"> 1</label>
      <label><input type="radio" name="rating" value="2"> 2</label>
      <label><input type="radio" name="rating" value="3"> 3</label>
      <label><input type="radio" name="rating" value="4"> 4</label>
      <label><input type="radio" name="rating" value="5"> 5</label>
      <span class="bz-rating__hint">1 = poor · 5 = great</span>
    </fieldset>
    <label>Severity (if something's wrong)
      <select name="severity">
        <option value="">— choose —</option>
        <option value="praise">👍 Praise</option>
        <option value="minor">Minor</option>
        <option value="major">Major</option>
        <option value="blocker">Blocker</option>
      </select>
    </label>
  </div>

  <label>What worked well?
    <textarea name="what_worked" rows="3" maxlength="4000" placeholder="What felt good or clear?"></textarea>
  </label>
  <label>What didn't work / was confusing?
    <textarea name="what_broke" rows="3" maxlength="4000" placeholder="Bugs, dead-ends, anything off…"></textarea>
  </label>
  <label>Suggestions
    <textarea name="suggestions" rows="3" maxlength="4000" placeholder="What would make it better?"></textarea>
  </label>

  <div class="bz-form__row">
    <label>Your name (optional)
      <input type="text" name="name" maxlength="150" placeholder="So we can follow up">
    </label>
    <label>Email (optional)
      <input type="email" name="email" maxlength="255" placeholder="you@example.com">
    </label>
  </div>

  <button type="submit" class="bz-btn bz-btn--primary" id="bz-submit">Send feedback</button>
  <p id="bz-result" class="bz-result" role="status" aria-live="polite"></p>
</form>

<script>
(function () {
  var API = "https://burnzone-api-prod-3cpbxepq4q-uc.a.run.app/api/v1/feedback";
  var form = document.getElementById("bz-feedback");
  if (!form) return;
  var result = document.getElementById("bz-result");
  var btn = document.getElementById("bz-submit");

  form.addEventListener("submit", function (e) {
    e.preventDefault();
    var fd = new FormData(form);
    var payload = {
      persona: fd.get("persona") || null,
      app: fd.get("app") || null,
      area: fd.get("area") || null,
      rating: fd.get("rating") ? Number(fd.get("rating")) : null,
      severity: fd.get("severity") || null,
      what_worked: fd.get("what_worked") || null,
      what_broke: fd.get("what_broke") || null,
      suggestions: fd.get("suggestions") || null,
      name: fd.get("name") || null,
      email: fd.get("email") || null,
      page_url: window.location.href
    };
    if (!payload.rating && !payload.what_worked && !payload.what_broke && !payload.suggestions) {
      result.className = "bz-result bz-result--err";
      result.textContent = "Please add a rating or a comment before sending.";
      return;
    }
    btn.disabled = true;
    result.className = "bz-result";
    result.textContent = "Sending…";
    fetch(API, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(payload)
    })
      .then(function (r) { return r.ok ? r.json() : r.json().then(function (j) { throw new Error(j.error || ("HTTP " + r.status)); }); })
      .then(function () {
        form.reset();
        result.className = "bz-result bz-result--ok";
        result.textContent = "🔥 Thanks! Your feedback was recorded.";
      })
      .catch(function (err) {
        result.className = "bz-result bz-result--err";
        result.textContent = "Couldn't send: " + err.message + ". Please try again.";
      })
      .finally(function () { btn.disabled = false; });
  });
})();
</script>
