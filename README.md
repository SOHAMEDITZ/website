<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form-Google Sheets</title>
    <style>
		 body {
     background: linear-gradient(
  135deg,
  #FF9933 0%,     /* Saffron */
  #FFFFFF 50%,    /* White */
  #138808 100%    /* Green */
);

      color: #fff;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 10px;
    }
    .form-container {
      background: #22223c;
      text-align: center;
      padding: 30px 28px;
      border-radius: 12px;
      box-shadow: 0 5px 18px rgba(0, 0, 0, 0.6);
      width: 100%;
      max-width: 420px;
  }
        form {
            max-width: 400px;
            margin: 10;
            padding: 30px;
            border: 1px solid #ccc;
            border-radius: 10px;
        }

        input[type="text"],
        input[type="email"],
        input[type="number"],
        input[type="password"],
        textarea {
            width: 90%;
            padding: 8px;
            margin: 5px 0 15px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        button {
      width: 100%;
      padding: 14px 0;
      background: #009ffd;
      color: #fff;
      font-weight: bold;
      font-size: 1.1em;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
        }
    </style>
</head>

<body>
	<div class="form-container">
	 <h2> SOHAM EDITZ 12</h2>
    <form id="sheetdb-form" action="https://sheetdb.io/api/v1/nb0wk0cs1z3r8" method="post">
        <input type="text" name="data[NAME]" id="uname" placeholder="Name">
        <input type="email" name="data[EMAIL]" id="uemail" placeholder="Password">   
         <button type="submit">Submit</button>
    </form>

    <script>
        var form = document.getElementById('sheetdb-form');
        form.addEventListener("submit", e => {
            e.preventDefault();
            fetch(form.action, {
                method: "POST",
                body: new FormData(document.getElementById("sheetdb-form")),
            }).then(
                response => response.json()
            ).then((html) => {
                alert('Submitted !! 😊 Thank you ' + document.getElementById('uname').value)
                window.location.href = '';
                location.reload();
            });
        });
    </script>
</body>

</html>
