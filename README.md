# web-panel-proxy
web-panel-proxy

Forked from https://github.com/POLESNIESOVETI12/web-panel-proxy

изменения

wpp_components.py:

Добавлен блок FORK SETTINGS с XRAY_REPO_PATH / OPENFLUX_REPO_PATH — URL релизов
KILL_SWITCH = /etc/web-proxy-panel/disable-auto-update — жёсткий выключатель
auto_status(): авто-апдейт теперь ВЫКЛ (config.get("enabled") is True вместо ... is not False)
Убрана строка config.update(enabled=True, ...) в конце run_auto_update() — она возвращала тумблер в «включено» после каждого цикла
set_auto_update() и run_auto_update() уважают kill-switch

wpp_update.py:

Блок FORK SETTINGS с REPO
KILL_SWITCH + проверки в auto_status(), set_auto_update(), start_update(automatic=True), run_update(), run_auto_update()

wpp_ui.py:1135:

automatic.enabled!==false → automatic.enabled===true (в componentView)
