+++
title = "Validate funding.json manifest online"
+++

<h1>Validate funding.json</h1>
<p>Validate your funding.json manifest syntactically and semantically by pasting the contents here.</p>


<section class="validate">
	<div class="message error"></div>
	<div class="message success">✓ Manifest is valid</div>
	<br />
	<form method="post" action="" class="validate">
		<div>
			<p>
				<label id="validate-url">Where will the manifest be hosted?</label>
				<input name="url" type="url" placeholder="https://example.com/funding.json" id="validate-url" required autofocus />
			</p>
			<p>
				<label for="validate-name">Manifest JSON body</label><br />
				<textarea name="body" id="validate-body" required placeholder="{}"></textarea>
			</p>
			<p>
				<button type="submit">Validate</button>
			</p>
		</div>
	</form>
</section>
