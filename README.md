# Grassphere
Shopify bespoke bundle product features for Grassphere Taiwan
<br />
<br />
I have omitted the rest of the files and only pushed the module's source code for demonstration purposes, 
showcasing my fluency and knowledge in Shopify Liquid, JavaScript and Shopify theme customization.<br />
<br />
<br />
The bundle is the best-selling product type in the store. The main idea behind it is to allow customers to mix and match various flavours in a single purchase. Customers can choose from options such as 15 packs, 30 packs, or 60 packs and then select their desired flavours and quantities until they reach the total number of packs. Finally, they can simply click "add to cart," and the unique flavour combination will be added to the cart instantly by calling Shopify Cart API.
<br />
<br />
We have chosen to leverage Shopify's new feature, metaobjects, to store the contents of each bundle and flavour variants. By centralizing the data using metaobjects, it greatly simplifies the workflow for the Grassphere team and enhances our overall experience.

You can find the entry point of the bundle module within the product section. If a bundle metaobject is assigned to a product, the bundle module will be rendered on that product page.

    <!-- Render bundle module conditionally -->
    {% assign bundleOBJ = product.metafields.custom.bundle_metaobj.value %}       
    {% if bundleOBJ != blank %}
      {% render 'bundle_module' bundleOBJ: bundleOBJ  %}
    {% endif %}
    
![image](https://github.com/MinreyP/Grassphere/assets/63085418/b1fb4347-da76-4be7-b902-4061887116b5)

The [bundle_module](https://github.com/MinreyP/Grassphere/blob/51b066336ee64c09189c1f13da48308b72ebfac7/snippets/bundle_module.liquid)
is a combination of Liquid templates and Vue. I believe this stack is the optimal choice to accomplish the mission, as it offers a lightweight solution that is easy to implement on top of an existing theme.
To achieve a better user experience (UX), I have dedicated a significant amount of time to meticulously crafting the triggering time and alert messages for users. My intention is to provide powerful features that can help merchants increase their sales conversion rate.

I have also separated the styling and feature logic, providing a much better experience for other developers on the team when it comes to maintaining the module.

