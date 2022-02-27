# aplinejs-spinbutton
Alpine JS Spinbutton component


```
 <script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
<!-- Usage -->
<span x-data="spinbutton">

    <-- Minus Button -->
    <button type="button" @click="minus" @keyup.down="minus"> - </button>

    <-- Output -->
    <output x-text="quantity"></output>

    <-- Plus Button -->
    <button type="button" @click="plus" @keyup.up="plus"> + </button>
</span>

<!-- Source -->
<script>
    document.addEventListener('alpine:init', () => {
        Alpine.data('spinbutton', (quantity) => ({
            quantity: 0,
            init(){
                this.quantity = quantity || 0
            },                       
            plus(){
                this.quantity++
            },
            minus(){
                if(this.quantity > 0){
                    this.quantity--    
                }
            }
        }))
    })
</script>
```