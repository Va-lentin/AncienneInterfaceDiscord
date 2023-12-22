# AncienneInterfaceDiscord
> *La nouvelle interface de Discord est dégeulasse, on est d'accord ?*

Guide :

- Rendez-vous sur <https://discord.com/app> depuis un navigateur __sur PC__ et connectez-vous à votre compte.
- Ouvrez la console de développeur (Ctrl + Shirt + I).
- Rendez-vous dans l'onglet "Console" et entrez le code suivant :
    ```js
    let wpRequire;
    window.webpackChunkdiscord_app.push([[ Math.random() ], {}, (req) => { wpRequire = req; }]);
    
    let UserSettingsActions = Object.values(wpRequire.c).find(x => x?.exports?.PreloadedUserSettingsActionCreators).exports;
    let ProtobufTypes = Object.values(wpRequire.c).find(x => x?.exports?.BoolValue).exports;
    
    UserSettingsActions.PreloadedUserSettingsActionCreators.updateAsync("appearance", data => {
        data.mobileRedesignDisabled = ProtobufTypes.BoolValue.create({value: true})
    }, UserSettingsActions.UserSettingsDelay.INFREQUENT_USER_ACTION)
    ```
*Crédits à [aamiaa](https://gist.github.com/aamiaa) pour avoir trouver cette méthode !* <3
