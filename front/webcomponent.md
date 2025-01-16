Un webcomponent permet de créer ses propres composants HTML en regroupant le CSS, le JS et l'HTML.

On utilise un `custom element` pour créer une balise avec un nom personnalisé.

ça va également créer un `shadow DOM` : un DOM qui est propre à l'élément et non accessible par le DOM principal.


Polyfill : bout de code permettant de fournir des fonctionnalités récentes à des anciens navigateurs (besoin d'avoir un polyfill web-component.js pour faire fonctionner les webcomponents sur d'anciens navigateurs)

La pseudo-classe :host permet de cibler l'hôte d'un shadow DOM contenant le CSS à utiliser pour cet hôte. Autrement dit, elle permet de sélectionner un élément personnalisé (custom element) depuis l'intérieur du shadow DOM. (source : https://developer.mozilla.org/fr/docs/Web/CSS/:host)
