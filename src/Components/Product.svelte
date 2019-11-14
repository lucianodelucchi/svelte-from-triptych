<script>
  import { cart } from "../Store/store.js";
  export let product = {};
  const setCart = () => cart.update(total => total + 1);
</script>

<div class="product">
  <picture>
    <img src={product.image} alt="" />
  </picture>
  <div class="product-info">
    <h1>{product.name}</h1>
    <h3>{product.description}</h3>
  </div>
  <div class="product-price">
    <p>{product.price}</p>
    {#if product.stock < 5}
      <strong>¡Hurry up!</strong>
    {/if}
  </div>
  <div class="addtocart">
    <button on:click={setCart}>Add to cart</button>
  </div>
</div>
