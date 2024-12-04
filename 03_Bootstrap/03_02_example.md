

# 1 

![](image/Pasted%20image%2020241204220937.png)
 
```html
<!doctype html>
<html lang="de">
<head>
	<title>Bootstrap: Komponenten</title>
	<meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
	
	<!-- Bootstrap: CSS -->
	<link
		href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
		rel="stylesheet"
		integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN"
		crossorigin="anonymous">

</head>
<body style="padding: 20px">

<!-- Card -->
<div class="card" style="width: 32rem">

	<!-- Carousel -->
	<div id="carouselExample" class="carousel slide" data-bs-ride="carousel">
	
		<!-- Carousel: Optionaler Indikator -->
		<div class="carousel-indicators">
			<li data-bs-target="#carouselExample" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></li>		 // aria-current="true", page reload 后 优先出现的是这个画面 
			<li data-bs-target="#carouselExample" data-bs-slide-to="1" aria-label="Slide 2"></li>
			<li data-bs-target="#carouselExample" data-bs-slide-to="2" aria-label="Slide 3"></li>
		</div>

		<!-- Carousel: Kern -->
		<div class="carousel-inner">
			<div class="carousel-item active">
				<img src="img/alps_carousel.jpg" class="d-block w-100" alt="Alpen">
			</div>
			<div class="carousel-item">
				<img src="img/fuji_carousel.jpg" class="d-block w-100" alt="Fuji">
			</div>
			<div class="carousel-item">
				<img src="img/norway_carousel.jpg" class="d-block w-100" alt="Norwegen">
			</div>
		</div>

		<!-- Carousel: optionale Controls -->
		<button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
			<span class="carousel-control-prev-icon" aria-hidden="true"></span>
			<span class="visually-hidden">Züruck</span>
		</button>
		<button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
			<span class="carousel-control-next-icon" aria-hidden="true"></span>
			<span class="visually-hidden">Weiter</span>
		</button>

	</div>
<!-- Ende Carousel -->

<!-- Card: Body-->
	<div class="card-body">
		<h5 class="card-title">Du willst Urlaub?</h5>
		<p class="card-text">

    <!-- Form (Bootstrap 5.3) -->
    <form>
	    <div class="mb-3">
		    <label for="mail2" class="form-label">
	        Registriere dich jetzt für unseren Newsletter!
        </label>
	      <input type="email" class="form-control" id="mail2" aria-describedby="emailHelp" placeholder="example@mail.com">
        <div id="emailHelp" class="form-text">
	        Natürlich bewahren wir deine E-Mailadresse sicher auf.</div>
        </div>
     </form>
                                                     <!-- siehe unten -->       <!-- siehe unten -->
			<button type="submit" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#modalExample">            
				Registrieren
			</button>
		</p>
	</div>
</div>
<!-- Ende Card -->

<!-- Modal -->
<div class="modal fade" id="modalExample" tabindex="-1" aria-labelledby="modallabel" aria-hidden="true">
	<div class="modal-dialog">
		<div class="modal-content">
			<div class="modal-header">
				<h5 class="modal-title" id="modalLabel">Registierung erfolgreich</h5>
				<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
			</div>
			<div class="modal-body">
				Willkommen beim tollen Urlaubs-Newsletter
			</div>
			<div class="modal-footer">
				<button type="button" class="btn btn-success" data-bs-dismiss="modal">
					Schließen
				</button>
			</div>
		</div>
	</div>
</div>


<!-- Bootstrap: benötigtes JS -->
<script
	src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
	integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
	crossorigin="anonymous"></script>
</body>

</html>
```

用到的 component

- card
- form 
- carousel
	- image-carousel
	- image vorrest angezeigt , when page reload  
	- aria-current attribute   
- button 
- modal
    - when man das model angeklickt, dann taucht eine fenster auf 


In Bootstrap sind data-bs-toggle und data-bs-target HTML-Datenattribute, die interaktive Elemente steuern:
- data-bs-toggle: Gibt den Typ der Bootstrap-Komponente an (z. B. modal, collapse, dropdown), die beim Klicken aktiviert werden soll.
- data-bs-target: Gibt das Ziel-Element an (meistens über id), auf das die Aktion angewendet werden soll.



