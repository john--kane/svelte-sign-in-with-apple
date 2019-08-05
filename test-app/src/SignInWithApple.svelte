<svelte:head>
    <meta name="appleid-signin-client-id" content="{clientId}">
    <meta name="appleid-signin-scope" content="{scope}">
    <meta name="appleid-signin-redirect-uri" content="{redirectURI}">
    <meta name="appleid-signin-state" content="{state}">
</svelte:head>

<style>
 .signin-button {
    width: 210px;
    height: 40px;
    cursor: pointer;
}
</style>

<div id="appleid-signin" class="signin-button" data-color="{color}" data-border="{border}" data-type="{type}"></div>

<script type="text/javascript">
// Meta tag values
    export let clientId = '[CLIENTID]';
    export let scope = '[SCOPE]';
    export let redirectURI= '[REDIRECT_URI]';
    export let state= '[STATE]';

// data types

    export let type = 'sign in'; // can only be 'sign in' and 'continue'
    export let color = 'black'; // can only be 'black' and 'white'
    export let border = 'false'; // can only be 'true in' and 'false'
    

    AppleID.auth.init({
        clientId : clientId,
        scope : scope,
        redirectURI: redirectURI,
        state : state
    });
</script>