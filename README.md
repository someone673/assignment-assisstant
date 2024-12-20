<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Learning Portal</title>
  <style>
    /* General Styles */
    body {
      font-family: Arial, sans-serif;
      font-weight: bold;
      margin: 0;
      padding: 0;
      background-color: #f8fafd;
      border-top-left-radius: 8%;
      border-top-right-radius: 8%;
    }

    /* Welcome Section (Home Page) */
    .welcome-section {
      background-image: url('https://img.freepik.com/premium-vector/illustration-culture-reading-books_604090-53.jpg');
'); /* Add your own image URL here */
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      text-align: center;
      color: #202020;
      padding: 100px 20px;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      transition: all 0.5s ease-in-out;
    }

    .welcome-section.blur {
      filter: blur(10px);
      pointer-events: none; /* Disable interactions while blurred */
    }

    .welcome-section h1 {
      font-size: 48px;
      margin-bottom: 20px;
    }

    .welcome-section p {
      font-size: 22px;
      margin-bottom: 40px;
      max-width: 800px;
      text-align: center;
    }

    .welcome-section button {
      padding: 15px 25px;
      background-color: #ff5722;
      border: none;
      color: white;
      font-size: 20px;
      font-weight: bold;
      cursor: pointer;
      border-radius: 5px;
      transition: background-color 0.3s;
    }

    .welcome-section button:hover {
      background-color: #e64a19;
    }

    /* Parallax Scrolling Section */
    .parallax {
      background-image: url('https://img.freepik.com/premium-photo/flat-cartoon-style-engaged-student-focus-curiosity-enthusiasm-learning_980716-171802.jpg'); /* Add your parallax image URL */
      height: 100vh;
      background-attachment: fixed;
      background-size: cover;
      background-position: center;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: rgb(29, 27, 27);
      font-size: 40px;
      font-weight: bold;
      padding: 0 20px;
    }

    /* Form Section */
    .form-section {
      background-color: white;
      padding: 50px 20px;
      max-width: 800px;
      margin: 50px auto;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
      opacity: 0;
      transform: translateY(50px);
      transition: all 1s ease;
    }

    .form-section.visible {
      opacity: 1;
      transform: translateY(0);
    }

    label {
      font-size: 16px;
      margin: 10px 0 5px;
      display: block;
    }

    input, select, textarea, button {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 16px;
    }

    button {
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    .thank-you-message {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      font-size: 24px;
      color: #4caf50;
      background-color: rgba(0, 0, 0, 0.7);
      padding: 20px;
      border-radius: 10px;
      width: 80%;
      max-width: 500px;
      display: none;
      opacity: 0;
      transition: opacity 10s ease;
    }

  </style>
</head>
<body>

  <!-- Welcome Section (Home Page) -->
  <div class="welcome-section" id="welcomeSection">
    <h1 >ዉድ ተማሪዎች እንኳን በደህና መጣችሁ!! </h1>
    <p>በክላስ መደራረብ ፣ በፈተናዎች መብዛት እና በተለያዩ ምክንያቶች አሳይመንት መስራት አልቻላችሁም ?</p>
    <p>እኛ ጋ በዘርፉ ልምድ ያካበቱ ቀለሜ ተማሪዎች እናንተን ለማስተናገድ ዝግጅታቸዉን ጨርሰዎል !   
        በተመጣጣኝ ክፍያ እንከን አልባ አዘገጃጀትን ከፈለጉ ምርጫ አልተሳሳታችሁም ትክክለኛዉ ቦታ ይህ ነዉ።</p>
    <button id="getStartedBtn">ይህንን በመጫን ትዕዛዝ ያስቀምጡ</button>
  </div>

  <!-- Parallax Scrolling Section -->
  <div class="parallax">
    <div>
      <h2>Ready to Submit Your Request?</h2>
      <p>Scroll down to submit your details and get the help you need.</p>
      <p>We are here to assist you, focus on your study.</p>
    </div>
  </div>

  <!-- Form Section -->
  <div class="form-section" id="formSection">
    <form id="dataForm">
      <label for="name">ስም:</label>
      <input type="text" id="name" name="name" placeholder="ስም አስገቡ" required>

      <label for="contact">ስልክ ቁጥር:</label>
      <input type="text" id="contact" name="contact" placeholder="ስልክ ቁጥር አስገቡ" required>

      <label for="category">ማሰራት የምትፈልጉት:</label>
      <select id="category" name="category" required>
        <option value="assignment">Assignment</option>
        <option value="literature_review">Literature Review</option>
        <option value="lab_report">Lab Report</option>
        <option value="others">Other</option>
      </select>

      <label for="message">Additional Notes:</label>
      <textarea id="message" name="message" placeholder="እንዲሰራላችሁ የምትፈልጉትን assignment , lab report , literature review , research እና ሌሎችንም ... ገለፃ እዚህ ጋ አስቀምጡ 😍" rows="4"></textarea>

      <button type="submit">Submit</button>
      <div class="message" id="status"></div>
    </form>
  </div>

  <!-- Thank You Message -->
  <div id="thankYouMessage" class="thank-you-message">
    ✅ዉድ ደምበኛችን በተሳካ ሁኔታ አጠናቅቀዋል፤ መልስ እስክንሰጥዎ እባክዎትን በ ተዕግስት ይጠብቁ እናመሰግናለን።
  </div>

  <script>
    const BOT_TOKEN = "7427881069:AAHLzG7fOUO-cJ6B2IMNuz3EJMeonN4jWWA"; // Your bot token
    const CHAT_ID = "972344877"; // Your chat ID

    const welcomeSection = document.getElementById("welcomeSection");
    const formSection = document.getElementById("formSection");
    const statusDiv = document.getElementById("status");
    const getStartedBtn = document.getElementById("getStartedBtn");
    const thankYouMessage = document.getElementById("thankYouMessage");

    // Blur and scroll effect
    getStartedBtn.addEventListener("click", () => {
      welcomeSection.classList.add("blur");
      formSection.classList.add("visible");
      window.scrollTo({
        top: formSection.offsetTop - 50,
        behavior: "smooth"
      });
    });

    // Form submission logic
    const form = document.getElementById("dataForm");

    form.addEventListener("submit", async (event) => {
      event.preventDefault();

      // Gather form data
      const name = document.getElementById("name").value;
      const contact = document.getElementById("contact").value;
      const category = document.getElementById("category").value;
      const message = document.getElementById("message").value;

      const telegramMessage = `New Request from Student:\n- Name: ${name}\n- Contact Info: ${contact}\n- Need Category: ${category}\n- Additional Notes: ${message}`;

      const TELEGRAM_URL = `https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`;

      try {
        const response = await fetch(TELEGRAM_URL, {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            chat_id: CHAT_ID,
            text: telegramMessage,
          }),
        });

        if (response.ok) {
          thankYouMessage.style.display = "block";
          thankYouMessage.style.opacity = "1";

          setTimeout(() => {
            thankYouMessage.style.opacity = "0";
            setTimeout(() => {
              thankYouMessage.style.display = "none";
              form.reset();
              window.scrollTo({ top: 0, behavior: "smooth" });
              welcomeSection.classList.remove("blur");
            }, 1000);
          }, 5000);
        } else {
          const result = await response.json();
          statusDiv.textContent = `❌ Error: ${result.description || "Something went wrong."}`;
          statusDiv.style.color = "red";
        }
      } catch (error) {
        console.error("Error:", error);
        statusDiv.textContent = "❌ An error occurred. Please try again.";
        statusDiv.style.color = "red";
      }
    });
  </script>

</body>
</html>
