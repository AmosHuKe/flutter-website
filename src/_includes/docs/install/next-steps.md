## Manage your Flutter SDK

To learn more about managing your Flutter SDK install,
consult the following resources.

{% assign choice = include.config %}
{% assign next-step = doctor[include.config] %}
{% assign mod-target = include.target | remove: 'mobile-' | downcase %}
{% if mod-target == 'desktop' %}
  {% assign webtarget = include.devos | append: '-desktop' | downcase %}
  {% assign andtarget = include.devos | downcase %}
  {% assign mod-target = include.devos | downcase %}
{% elsif mod-target == 'web' %}
  {% assign andtarget = 'web-on-' | append: include.devos | downcase %}
{% else %}
  {% assign webtarget = mod-target | append: '-on-' | append: include.devos | downcase %}
  {% assign andtarget = include.devos | downcase %}
{% endif %}

* [Upgrade Flutter][upgrade]
{%- case next-step.add-android %}
{%- when 'Y' %}
* [Add Android compilation tools](/platform-integration/android/setup)
{%- endcase %}
{%- case next-step.add-chrome %}
{%- when 'Y' %}
* [Add web as a build target](/platform-integration/web/setup)
{%- endcase %}
{%- case next-step.add-simulator %}
{%- when 'Y' %}
* [Add iOS simulator or device](/platform-integration/ios/setup)
{%- endcase %}
{%- case next-step.add-xcode %}
{%- when 'Y' %}
* [Add macOS compilation tools](/platform-integration/macos/setup)
{%- endcase %}
{%- case next-step.add-linux-tools %}
{%- when 'Y' %}
* [Add Linux compilation tools](/platform-integration/linux/setup)
{%- endcase %}
{%- case next-step.add-visual-studio %}
{%- when 'Y' %}
* [Add Windows desktop compilation tools](/platform-integration/windows/setup)
{%- endcase %}
* [Uninstall Flutter][uninstall]

[upgrade]: /install/upgrade
[uninstall]: /install/uninstall?tab-save-dev-os={{include.devos}}
