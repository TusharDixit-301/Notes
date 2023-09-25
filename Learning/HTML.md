# Semantic HTML 

## HTML should be written in this way : 

<img src="https://static.semrush.com/blog/uploads/media/cc/85/cc85d452a743e27f68d426df35e4da7d/EN-Semantic-Search-Non-Semantic.webp">

**Example :** 

```HTML
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<meta name="author" content="Tushar Dixit" />
		<meta name="description" content="Official Website for Little Taco Shop" />
		<title>Little Taco Shop</title>
		<link rel="icon" href="favicon.ico" type="image/x-icon" />
		<link rel="stylesheet" href="css/style.css" />
	</head>
	<body>
		<header>
			<h1>First Heading</h1>
			<nav>
				<!-- Navigation goes here -->
			</nav>
		</header>
		<main>
			<article>
				<section>
					<!-- Various section goes here -->
				</section>
			</article>
		</main>
		<footer>
			<!-- Footer here -->
		</footer>
	</body>
</html>
```

## Images 
Every Image should be inside a `<figure>` Tag which gives it more meaning.
**Examples :** 
```HTML
<figure>
				<img
					src="SOURCE"
					alt="Tacos Image"
					height="267"
					width="400"
					title="We love tacos"
				/>
				<figcaption>Tacos and a Drink</figcaption>
</figure>
```