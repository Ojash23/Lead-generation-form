<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>N8N Lead Capture Form</title>
  <style>
    body {font-family:'Segoe UI',sans-serif; background:#f4f6f8; display:flex;justify-content:center;align-items:center;min-height:100vh;margin:0;}
    .form-container {background:white;padding:30px;border-radius:10px;box-shadow:0 4px 12px rgba(0,0,0,0.1);max-width:500px;width:100%;}
    h2 {margin-top:0;color:#333;text-align:center;}
    .form-group {margin-bottom:15px;}
    label {display:block;margin-bottom:5px;color:#555;}
    input,textarea {width:100%;padding:10px;border:1px solid #ccc;border-radius:5px;font-size:14px;}
    .submit-btn {width:100%;padding:12px;background:#667eea;color:white;border:none;border-radius:5px;font-size:16px;cursor:pointer;}
    .submit-btn:hover {background:#5a67d8;}
    .success-message {display:none;padding:15px;background:#d4edda;color:#155724;border-radius:5px;text-align:center;}
  </style>
</head>
<body>
  <div class="form-container">
    <h2>Contact Us</h2>
    <form id="leadForm">
      <div class="form-group">
        <label for="name">Name *</label>
        <input type="text" id="name" name="name" required>
      </div>
      <div class="form-group">
        <label for="email">Email *</label>
        <input type="email" id="email" name="email" required>
      </div>
      <div class="form-group">
        <label for="message">Message *</label>
        <textarea id="message" name="message" rows="4" required></textarea>
      </div>
      <button type="submit" class="submit-btn">Send Message</button>
    </form>
    <div id="successMessage" class="success-message">
      ✅ Thank you! We'll get back to you soon.
    </div>
  </div>

  <script>
    document.getElementById('leadForm').addEventListener('submit', async function(e) {
      e.preventDefault();
      const formData = { 
        name: this.name.value,
        email: this.email.value,
        message: this.message.value,
        source: 'GitHub Pages Form',
        timestamp: new Date().toISOString()
      };  
      try {
        const res = await fetch('YOUR_N8N_WEBHOOK_URL_HERE', {
          method: 'POST', headers:{'Content-Type':'application/json'}, body: JSON.stringify(formData)
        });
        if (res.ok) {document.getElementById('successMessage').style.display='block'; this.style.display='none';}
        else throw new Error('Network error');
      } catch (err) {alert('Error sending message.'); console.error(err);}  
    });
  </script>
</body>
</html>