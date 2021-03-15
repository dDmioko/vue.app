<template>
    <form>
        <label>Email:</label>
        <input type="email" required />
    </form>
</template>

<script>
export default {};
</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
    padding: 40px;
    border-radius: 10px;
    background: white;
    text-align: left;
}
label {
    display: inline-block;
    margin: 25px 0 15px;
    color: #aaa;
    font-size: 0.6em;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
}
input {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}
</style>
