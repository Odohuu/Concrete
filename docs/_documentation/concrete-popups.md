---
title:  "Concrete Popups"
handle: "concrete-popups"
category: "javascript modules"
---
By default Concrete has three popups; cart, address and errors. These are located in the snippets directory and are always prefixed with `popup-`.

Creating a new popup is very easy, here is the basic structure:

{% highlight html %}
{% raw %}
<div id="PopupNew" class="popup overlay">
  <div class="popup-inner">
    <div class="popup-content left">

      <h1>New Popup</h1>

      <a href="#close" class="popup-close" data-close aria-label="{{ 'common.close' | t }}">{% include 'icon' with 'close' %}</a>
    </div>
  </div>
</div>

<script>
  var newPopup = new Concrete.Popup('#PopupNew');
</script>
{% endraw %}
{% endhighlight %}

This will create a basic popup with a heading and a close button. Now we want to display the popup every time someone clicks an element.

{% highlight html %}
<button data-trigger="popup" data-target="#PopupNew">Click Me</button>
{% endhighlight %}

##### Selectors
 - `data-trigger="popup"` Defines an element that will trigger a popup when clicked.
 - `data-target="#examplePopup"` Defines the popup that we are targetting.
 - `data-close` Closes the current popup.

##### jQuery Events
  The following events occur when opening, closing, or toggling a popup.

| Event        | Parameters          | Description      |
| ------------ | ------------------- | ---------------- |
| `concrete:popup:open`     | None | Fires when a popup has finished opening |
| `concrete:popup:close`    | None     |   Fires when a popup has finished closing |
| `concrete:popup:error` | error (String)      | Fires when an event cannt open or close. Passes the error the event |
