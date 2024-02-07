<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TopTees</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em;
        }

        nav {
            display: flex;
            justify-content: center;
            background-color: #444;
            padding: 0.5em;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-weight: bold;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .product-card {
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            margin: 20px;
            float: left;
            width: calc(33.3333% - 40px);
            box-sizing: border-box;
            background-color: white;
            transition: transform 0.3s;
        }

        .product-card:hover {
            transform: scale(1.05);
        }

        .product-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .product-info {
            padding: 15px;
        }

        .product-title {
            font-size: 1.2em;
            margin-bottom: 10px;
        }

        .product-price {
            font-size: 1.1em;
            color: #007BFF;
        }
    </style>
</head>
<body>
    <header>
        <h1>TopTees</h1>
    </header>

    <nav>
        <a href="#">Home</a>
        <a href="#">Products</a>
        <a href="#">Contact</a>
    </nav>

    <div class="container" id="productContainer">
        <!-- Product cards will be dynamically added here -->
    </div>

    <script>
        // Function to generate product cards
        function generateProductCards(numberOfProducts) {
            var container = document.getElementById("productContainer");

            for (var i = 1; i <= numberOfProducts; i++) {
                var productCard = document.createElement("div");
                productCard.className = "product-card";

                var productImage = document.createElement("img");
                productImage.className = "product-image";
                productImage.src = "product" + i + ".jpg";
                productImage.alt = "Product " + i;

                var productInfo = document.createElement("div");
                productInfo.className = "product-info";

                var productTitle = document.createElement("div");
                productTitle.className = "product-title";
                productTitle.textContent = "Product " + i;

                var productPrice = document.createElement("div");
                productPrice.className = "product-price";
                productPrice.textContent = "$" + (10 + i * 5).toFixed(2); // Adjust pricing logic as needed

                var addToCartButton = document.createElement("button");
                addToCartButton.textContent = "Add to Cart";
                addToCartButton.onclick = function () {
                    addToCart(i);
                };

                productInfo.appendChild(productTitle);
                productInfo.appendChild(productPrice);
                productInfo.appendChild(addToCartButton);

                productCard.appendChild(productImage);
                productCard.appendChild(productInfo);

                container.appendChild(productCard);
            }
        }

        // Call the function to generate 1000 product cards
        generateProductCards(99);

        function addToCart(productId) {
            // Add your JavaScript logic for adding the product to the cart here
            alert('Product ' + productId + ' added to cart!');
        }
    </script>
</body>
</html>
