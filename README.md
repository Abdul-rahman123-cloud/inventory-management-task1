📦 Inventory Management (HTML + JavaScript + Bootstrap)

This is a simple inventory management frontend built with vanilla HTML, CSS, JavaScript, and Bootstrap (tier 1). It connects directly to two AWS Lambda Function URLs (via HTTP) (tier 2) that interact with a DynamoDB table (tier 3) named inventory-db.
🔧 Features

    🔄 Fetch and display all inventory items
    ➕ Add a new product (product_name, quantity)
    🔁 Update the quantity of an existing product using product_id
    🌐 No frameworks required — works entirely in a browser
    💡 Clean, responsive UI powered by Bootstrap 5

📂 How to Use

    Clone or download this repository.
    Open the index.html file in any web browser (double-click it or right-click > Open With > Browser).
    Use the interface to:
        Refresh the current inventory list.
        Add new products.
        Update existing product quantities.

    ⚠️ This app depends on two pre-configured AWS Lambda functions with public URLs that handle the backend logic (adding, updating, and fetching items from DynamoDB). If you'd like to set up your own backend, see below.

🌐 Backend Configuration (Optional)

This project was designed to work with two serverless Lambda function URLs:

    https://ya5t24xky6tgjpl6ohckb42ljq0tysdn.lambda-url.us-east-1.on.aws/
    → Handles add_item and update_item actions.

    https://lgxymwdzhitho5nglp3se4gfce0yposx.lambda-url.us-east-1.on.aws/
    → Fetches all items from the inventory-db table.

Both Lambda functions interact with an AWS DynamoDB table structured like this:
Attribute	Type	Description
product_id	String	Partition Key, auto-generated
product_name	String	Name of the product
quantity	Number	Quantity available
