/* script.js
   English variable names and comments
   - Hash-based routing (#/path)
   - Seasonal background toggle
   - Instructions inside comments show where to add pages and content
   - Use tabs for indentation
*/

/* -----------------------------
   CONFIG
   -----------------------------
   Set backgroundEffect to "snow", "fall" or null
   - "snow" uses assets/snowflake.png
   - "fall" uses assets/leaf.png
   - null disables seasonal canvas
*/
const backgroundEffect = "none" // "snow" | "fall" | null

/* Floating primary button configuration
   - url: can be external or route (use #/route for local hashes)
   - label: visible text
*/
const floatingButtonConfig = {
	url: "#/rules",
	label: "Правила"
}

/* -----------------------------
   ROUTES / TEMPLATES
   -----------------------------
   Add or change page templates here.
   Key = route fragment (after #/). Use "" or "/" for home.
   Template is a function returning HTML string

   Карточка Steam пример:
   --------------
   			<div class="grid">
				<div class="card steam-card">
					<div class="thumb">
						<!-- placeholder image: change to your steam item -->
						<img src="assets/images.jpg" alt="Steam item thumbnail" />
					</div>
					<div>
						<h3>название: </h3>
						<p>краткое описание</p>
						<p><small>Добавлено: 2025-01-01 · Владелец: Команда Sandbox</small></p>
					</div>
				</div>
			</div>
*/
const templates = {
	"": () => {
		return `
		<section class="card">
			<h2>Добро пожаловать в Фенрир Sanbox</h2>
			<p>IP: 62.122.214.169:27015.</p>
			<div class="separator" role="separator"></div>

			<h3>Быстрые ссылки</h3>
			<div class="kv">
				<a class="badge" href="#/steam">Обновления</a>
                <a class="badge" href="#/collection">Коллекция</a>
				<a class="badge" href="#/admin-rules">Правила админов</a>
				<a class="badge" href="#/rules">Правила</a>
			</div>

			<div style="height:14px"></div>
			<!-- <h3>Заходите на наш сервер!</h3>  -->
		</section>
		<p></p>
		<section class="card">
			<h2>Discord</h2>
			<p>Присоединяйтесь к нашему Discord для обновлений и поддержки</p>
			<p><a class="badge" href="https://discord.gg/your-invite" target="_blank" rel="noopener">Открыть приглашение в Discord</a></p>
		</section>	
		<p></p>
		<section class="card">
			<h2>Часто задаваемые вопросы</h2>
			<h3>Почему меня забанили?</h3>
			<p>Прочтите <a class="badge" href="#/rules">Правила</a> выше и сверьтесь с причиной бана в сообщении при заходе на сервер или в сообщении от бота в Discord.</p>
			<h3>Как подать жалобу?</h3>
			<p>Используйте Discord или команду жалобы в игре. Предоставьте скриншоты и стимайди нарушителя модератору.</p>
    		<h3>Я больше так не буду, разбаньте пожалуйста!</h3>
			<p>Используйте Discord для подачи аппеляций на разбан.</p>
		</section>
		`
	},

	"rules": () => {
		return `
		<section class="card">
			<h2>Общие правила</h2>
			<p>Символ "→" обозначает следующее наказание<br>Вместо наказания может быть выдано предупреждение, если нарушение не приводит к перманентному бану<br><br>Будьте человечны, используйте здравый смысл, критическое мышление и уважайте других игроков. <br>Даже если ваши действия напрямую не подпадают под конкретный пункт правил, но приносят деструктив, мешают игрокам или нарушают работу сервера, модерация имеет право оценивать ситуацию на своё усмотрение.<br><br>Это работает и наоборот - если ваши действия не мешают другим игрокам или работе сервера, модерация в праве игнорировать такие нарушения.<br><br>Так-же модерация является теми, кто устанавливает понятие баланса при проверках построек. Если вы не согласны с мнением модератора, вы имеете право написать на него жалобу в <a class="badge" href="https://discord.gg/your-invite" target="_blank" rel="noopener">Discord</a><br><br></p>

			<table class="simple-table" aria-label="rules table">
				<thead><tr><th>Основные Правила</th><th>Наказание</th></tr></thead>
				<tbody>
					<tr><td>1.1. Запрещено вмешиваться в работу сервера посредством умышленного создания лагов/краша, использования любых эксплоитов игры</td><td>Перманентный бан</td></tr>
					<tr><td>1.2. Запрещено вмешиваться в игровой процесс или мешать проведению ивентов<br>Под помехой понимаются любые активные действия, которые усложняют игру другим игрокам: толкание или убийство пропами используя физган, частичное или полное блокирование публичных зон или основных маршрутов на карте, создания блиндеров и подобные действия<br>Билд-Мод не имеет право мешать ПВП-Моду и наоборот.</td><td>Предупреждение → Джайл до 30мин → Бан до 7 дней</td></tr>
					<tr><td>1.3. Запрещено использование сторонних программ или читов, дающих преимущество в PvP.</td><td>Перманентный бан</td></tr>
				    <tr><td>1.4. Запрещён обход выданного наказания или попытка помешать процессу разбора жалоб.</td><td>Увеличенный срок наказания x2 → Бан 5 дней</td></tr>
                    <tr><td>1.5. Запрещён ERP, спам или флуд сообщениями либо проигрывание громких, неприятных звуков в голосовом чате.</td><td>Предупреждение → Гаг/Мут до 10 минут → Джайл+Гаг/Мут до 1 часа</td></tr>
                    <tr><td>1.6. Запрещены призывы к самобичеванию, обсуждение политики, разжигание розни или иной вражды.</td><td>Бан до 7 дней → Перманентный бан</td></tr>
                    <tr><td>1.7. Запрещена реклама во всех своих проявлениях без разрешения Создателя сервера.</td><td>Перманентный бан</td></tr>
                    <tr><td>1.8. Запрещено использование или распространение эротического контента (модели, картинки, pac3, т.д.).</td><td>Предупреждение / Бан 7 дней в зависимости от ситуцаии</td></tr>
                </tbody>
			</table>
        </section>

			<div class="separator"></div>

		<section class="card">	
            <table class="simple-table" aria-label="pvprules table">
				<thead><tr><th>Правила ПВП-Мода</th><th>Наказание</th></tr></thead>
				<tbody>
					<tr><td>2.1. Запрещается застраивать свою базу без возможности проникновения</td><td>Предупреждение → Удаление постройки → Джайл до 30 минут</td></tr>
					<tr><td>2.2. Запрещается использовать дизбалансные сооружения с помощью Wire, E2, PAC3, ACF и других аддонов.<br>Запрещены телепорты для убийств, сильное изменение характеристик игрока, любые неуничтожимые или полностью автоматические системы (турели/дроны/механизмы),<br>турели без уязвимого оператора внутри или без отключения после смерти оператора,<br>чрезмерные скопления или ваншот-турели, непробиваемая броня, слишком мощное оружие, невидимость через E2 и похожие конструкции.</td><td>Предупреждение → Джайл до 30мин → Бан до 7 дней (Возможный e2-бан или pac3-бан)</td></tr>
					<tr><td>2.3. Запрещено использование сторонних программ или читов, дающих преимущество в PvP.</td><td>Перманентный бан</td></tr>
                    <tr><td>2.4. Запрещены модели Outfitter ниже GMOD модели male_07.</td><td>Предупреждение → Джайл до 30 минут → Бан 1 день</td></tr>
                    <tr><td>2.5. Запрещён абуз техникой/конструкциями<br>Например, удаляя полуразрушенную/разрушенную единицу техники или постройку и создание новой мгновенно. Должно пройти +-30 секунд перед повторным созданием после удаления.</td><td>Предупреждение → Джайл до 30 минут → Бан до 2 дней</td></tr>
                </tbody>
			</table>
        </section>

            <div class="separator"></div>

        <section class="card">
            <table class="simple-table" aria-label="raidrules table">
				<thead><tr><th>Правила рейдов</th><th>Наказание</th></tr></thead>
				<tbody>
					<tr><td>3.1. Запрещено прятать, использовать Fading Door для перестрелок путём быстрого закрытия/открытия либо для помехи в взломе.<br>Минимальное время открытого состояния 5 секунд.</td><td>Предупреждение → Удаление постройки → Джайл до 30 минут</td></tr>
					<tr><td>3.2. Запрещено строить корридоры смерти, труднопроходимые конструкции<br>Например проход, в котором можно пройти только сидя.</td><td>Предупреждение → Джайл до 30мин → Бан до 2 дней</td></tr>
                </tbody>
			</table>
        </section>

			<div class="separator"></div>
        <br>
		`
	},

    "admin-rules": () => {
        return `
        <section class="card">
            <h2>Обязанности администрации</h2>
            <p>Каждая роль имеет свои задачи и ответственность на сервере</p>

            <table class="simple-table" aria-label="admin duties table">
                <thead><tr><th>Роль</th><th>Обязанности</th></tr></thead>
                <tbody>
                    <tr><td>Младший модератор</td><td>Следит за соблюдением правил игроками и поддерживает порядок</td></tr>
                    <tr><td>Модератор</td><td>Разбирает нарушения, выносит наказания, следит за порядком</td></tr>
                    <tr><td>Администратор</td><td>Обнаруживает баги, докладывает в канал «Нет доступа», следит за порядком на сервере</td></tr>
                    <tr><td>Главный Администратор</td><td>Управляет отделом администраторов и модераторов, заменяет Куратора при необходимости</td></tr>
                    <tr><td>Тестировщик</td><td>От лица игрока выявляет причины лагов, крашей и нестабильной работы</td></tr>
                    <tr><td>Главный Тестер</td><td>Координирует тестировщиков и передаёт найденные проблемы в «Нет доступа»</td></tr>
                    <tr><td>Доверенный</td><td>Оказывает активную помощь серверу, поддерживает связь с высшей администрацией</td></tr>
                    <tr><td>Куратор</td><td>Обеспечивает контроль над сервером и его стратегическое развитие</td></tr>
                    <tr><td>Совладелец</td><td>Помогает Владельцу, принимает решения и координирует работу высшей администрации</td></tr>
                    <tr><td>Владелец</td><td>Основатель проекта, отвечает за развитие и ключевые решения</td></tr>
                </tbody>
            </table>
        </section>

        <div class="separator"></div>

        <section class="card">
            <h2>Принципы работы администрации</h2>
            <ul>
                <li>Беспристрастность: объективная оценка и выслушивание обеих сторон</li>
                <li>Минимизация наказаний: сначала объяснения и предупреждения, строгие меры только при серьёзных нарушениях</li>
                <li>Использование полномочий строго по обязанностям, без личной выгоды</li>
                <li>Своевременное рассмотрение жалоб, обычно в течение 2 дней</li>
                <li>Обучение и контроль младших сотрудников старшими администраторами</li>
            </ul>

            <div class="separator"></div>
            <h3>Контакты администрации</h3>
            <p><small>Связь через <a href="#/discord">Discord</a></small></p>
        </section>
        `
    },

	"wiki": () => {
		return `
		<section class="card">
			<h2>Wiki - Кастомные функции</h2>
			<p>Таблица примеров функций для нашего сервера</p>

			<table class="simple-table" aria-label="wiki functions">
				<thead><tr><th>Function</th><th>Description</th></tr></thead>
				<tbody>
					<tr><td>spawn_item(pos, itemId)</td><td>Спавнит предмет по позиции и ID</td></tr>
					<tr><td>set_owner(entity, player)</td><td>Назначает владельца сущности игроку</td></tr>
				</tbody>
			</table>

			<div class="separator"></div>
			<h3>Заметки</h3>
			<p>Опишите параметры, возвращаемые значения и права доступа здесь</p>
		</section>
		`
	},

	"steam": () => {
		return `
		<section class="card">
			<h2>Обновления</h2>
			<p>Пример отображения обновления</p>
   			<div class="grid">
				<div class="card steam-card">
					<div class="thumb">
						<!-- placeholder image: change to your steam item -->
						<img src="assets/images.jpg" alt="Миниатюра обновления" />
					</div>
					<div>
						<h3>Название: </h3>
						<p>краткое описание</p>
						<p><small>Добавлено: 2025-01-01 · Владелец: Команда Sandbox</small></p>
					</div>
				</div>
			</div>
            <p></p>
   			<div class="grid">
				<div class="card steam-card">
					<div class="thumb">
						<!-- placeholder image: change to your steam item -->
						<img src="assets/images.jpg" alt="Миниатюра обновления" />
					</div>
					<div>
						<h3>Название: </h3>
						<p>краткое описание</p>
						<p><small>Добавлено: 2025-01-01 · Владелец: Команда Sandbox</small></p>
					</div>
				</div>
			</div>
		</section>
		`
	},
}

/* -----------------------------
   ROUTER
   -----------------------------
*/
function renderRoute(){
	const rawHash = (location.hash || "#/").replace(/^#/, "")
	const routeKey = rawHash.replace(/^\//, "")
	const template = templates[routeKey] || templates[""]
	const appEl = document.getElementById("app")
	appEl.innerHTML = template()
	// update active state in nav (optional)
	updateNavActive(routeKey)
}

/* Update nav active link (visual) */
function updateNavActive(routeKey){
	// simple approach: find all nav links and toggle aria-current
	document.querySelectorAll(".nav-list a").forEach(a => {
		const href = (a.getAttribute("href") || "")
		const linkRoute = href.replace(/^#\/?/, "")
		if(linkRoute === routeKey) a.setAttribute("aria-current", "page")
		else a.removeAttribute("aria-current")
	})
}

/* Initialize nav toggle for small screens */
function initNavToggle(){
	const toggle = document.getElementById("nav-toggle")
	const list = document.getElementById("nav-list")
	toggle.addEventListener("click", () => {
		const expanded = toggle.getAttribute("aria-expanded") === "true"
		toggle.setAttribute("aria-expanded", String(!expanded))
		list.classList.toggle("show")
	})
	// Close nav on link click (mobile)
	list.querySelectorAll("a").forEach(a => {
		a.addEventListener("click", () => {
			list.classList.remove("show")
			toggle.setAttribute("aria-expanded", "false")
		})
	})
}

/* Setup floating button */
function initFloatingButton(){
	const container = document.getElementById("floating-actions")
	const btn = document.getElementById("floating-primary")
	if(!floatingButtonConfig || !btn) return
	btn.setAttribute("href", floatingButtonConfig.url || "#/")
	btn.textContent = floatingButtonConfig.label || "Action"
}

/* Hash change listener */
window.addEventListener("hashchange", () => {
	renderRoute()
	window.scrollTo({top:0, behavior:"smooth"})
})

/* Initial run */
document.addEventListener("DOMContentLoaded", () => {
	// render page
	renderRoute()
	initNavToggle()
	initFloatingButton()

	// seasonal background initialization
	if(backgroundEffect === "snow" || backgroundEffect === "fall"){
		initSeasonalCanvas(backgroundEffect)
	}
})

/* -----------------------------
   SEASONAL CANVAS (lightweight)
   -----------------------------
   - Uses a single canvas element inside #seasonal-overlay
   - Draws falling sprites (snow or leaf)
   - Placeholder images: assets/snowflake.png and assets/leaf.png
   - Limited particle count for performance
   - Can be disabled by setting backgroundEffect = null
*/
function initSeasonalCanvas(effect){
	// ensure overlay exists
	const overlay = document.getElementById("seasonal-overlay")
	if(!overlay) return

	// remove old canvas if present
	const old = document.getElementById("seasonal-canvas")
	if(old) old.remove()

	const canvas = document.createElement("canvas")
	canvas.id = "seasonal-canvas"
	// inline safety styles (CSS handles most)
	canvas.style.position = "fixed"
	canvas.style.top = "0"
	canvas.style.left = "0"
	canvas.style.width = "100%"
	canvas.style.height = "100%"
	canvas.style.pointerEvents = "none"
	canvas.style.zIndex = "0"
	overlay.appendChild(canvas)

	const ctx = canvas.getContext("2d")
	let running = true

	// handle device pixel ratio for crisp rendering
	function setCanvasSize(){
		const dpr = window.devicePixelRatio || 1
		canvas.width = Math.floor(window.innerWidth * dpr)
		canvas.height = Math.floor(window.innerHeight * dpr)
		// draw operations use CSS pixels
		ctx.setTransform(dpr, 0, 0, dpr, 0, 0)
	}
	setCanvasSize()

	// sprite image for snow/leaf
	const sprite = new Image()
	sprite.src = effect === "leaf" ? "assets/snowflake.png" : "assets/leaf.png"

	// particles
	const maxParticles = 60
	const particles = []

	function createParticle(){
		const size = effect === "snow" ? (8 + Math.random()*10) : (18 + Math.random()*18)
		return {
			x: Math.random() * window.innerWidth,
			y: Math.random() * window.innerHeight * Math.random() - 50,
			speedY: (0.3 + Math.random()*1.1) * (effect === "snow" ? 0.6 : 1.1),
			speedX: (Math.random() - 0.5) * (effect === "snow" ? 0.3 : 0.6),
			size,
			rot: Math.random() * Math.PI * 2,
			rotSpeed: (Math.random()-0.5) * 0.02
		}
	}

	function createParticles(){
		particles.length = 0
		for(let i=0;i<maxParticles;i++){
			particles.push(createParticle())
		}
	}

	sprite.onload = () => { createParticles(); animate() }
	sprite.onerror = () => { createParticles(); animate() }

	// resize handling
	window.addEventListener("resize", () => {
		setCanvasSize()
		for(let p of particles){
			p.x = Math.min(p.x, window.innerWidth + 100)
			p.y = Math.min(p.y, window.innerHeight + 100)
		}
	})

	// pause when tab not visible
	document.addEventListener("visibilitychange", () => {
		running = document.visibilityState === "visible"
		if(running) animate()
	})

	function animate(){
		if(!running) return
		// clear in CSS pixels (context scaled)
		ctx.clearRect(0, 0, window.innerWidth, window.innerHeight)
		ctx.globalAlpha = 0.95

		for(let p of particles){
			p.y += p.speedY
			p.x += p.speedX
			p.rot += p.rotSpeed

			if(sprite.complete && sprite.naturalWidth > 0){
				ctx.save()
				ctx.translate(p.x, p.y)
				ctx.rotate(p.rot)
				ctx.drawImage(sprite, -p.size/2, -p.size/2, p.size, p.size)
				ctx.restore()
			} else {
				ctx.save()
				ctx.translate(p.x, p.y)
				ctx.rotate(p.rot)
				if(effect === "snow"){
					ctx.beginPath()
					ctx.arc(0, 0, Math.max(1, p.size/2), 0, Math.PI*2)
					ctx.fillStyle = "rgba(255,255,255,0.85)"
					ctx.fill()
				} else {
					ctx.fillStyle = "rgba(170,120,70,0.95)"
					ctx.fillRect(-p.size/2, -p.size/4, p.size, p.size/2)
				}
				ctx.restore()
			}

			// recycle offscreen
			if(p.y > window.innerHeight + 60 || p.x < -120 || p.x > window.innerWidth + 120){
				Object.assign(p, createParticle())
				p.y = -40
			}
		}

		window.requestAnimationFrame(animate)
	}

	// start if sprite already loaded
	if(sprite.complete){
		if(particles.length === 0) createParticles()
		animate()
	}
}


/* -----------------------------
   INSTRUCTIONS (code-level)
   -----------------------------
   - To add a new sub-page:
     1) Add a new key to the `templates` object above, for example:
        "about": () => `...html...`
     2) Add a link to the nav in index.html (or link using <a href="#/about">About</a>)
     3) Optionally adjust floatingButtonConfig to point to the new route
   - To change the seasonal effect:
     - Edit `backgroundEffect` at top of this file ("snow" | "fall" | null)
     - Replace placeholder images in /assets (assets/snowflake.png, assets/leaf.png)
   - To customize colors:
     - Edit CSS variables at the top of styles.css (:root section)
   - To change typography:
     - Edit --font-family or include a custom font in index.html (instructions below)
   - To change floating button position:
     - Edit .floating-actions in styles.css (e.g., left:20px; bottom:40px;)
*/

/* -----------------------------
   Optional: how to include custom fonts (do not include automatically)
   - Download font files and place in /assets/fonts/
   - Add to styles.css:
     @font-face {
     	font-family: "MyCustom";
     	src: url("assets/fonts/MyCustom-Regular.woff2") format("woff2");
     	font-weight: 400;
     	font-style: normal;
     	font-display: swap;
     }
     Then set --font-family: "MyCustom", system-ui, ...
   -----------------------------
*/
