In file included from H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:14:  
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c: In function 'mqtt_event_handler':  
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:265:27: error: format '%d' expects argument of type 'int', but argument 7 has type 'int32_t' {aka   'long int'} [-Werror=format=]
265 | #define LOG_COLOR(COLOR) "\033[0;" COLOR "m"
| ^~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:268:27: note: in expansion of macro 'LOG_COLOR'
268 | #define LOG_COLOR_E LOG_COLOR(LOG_COLOR_RED)
| ^~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:282:37: note: in expansion of macro 'LOG_COLOR_E'
282 | #define LOG_FORMAT(letter, format) LOG_COLOR_ ## letter #letter " (%" PRIu32 ") %s: " format LOG_RESET_COLOR "\n"
| ^~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:410:86: note: in expansion of macro 'LOG_FORMAT'
410 | if (level==ESP_LOG_ERROR ) { esp_log_write(ESP_LOG_ERROR, tag, LOG_FORMAT(E, format), esp_log_timestamp(), tag, ##VA_ARGS); } \
| ^~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:432:41: note: in expansion of macro 'ESP_LOG_LEVEL'
432 | if ( LOG_LOCAL_LEVEL >= level ) ESP_LOG_LEVEL(level, tag, format, ##VA_ARGS); \
| ^~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:343:38: note: in expansion of macro 'ESP_LOG_LEVEL_LOCAL'
343 | #define ESP_LOGD( tag, format, ... ) ESP_LOG_LEVEL_LOCAL(ESP_LOG_DEBUG, tag, format, ##VA_ARGS)
| ^~~~~~~~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:5: note: in expansion of macro 'ESP_LOGD'
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:265:27: error: format '%d' expects argument of type 'int', but argument 7 has type 'int32_t' {aka 'long int'} [-Werror=format=]
265 | #define LOG_COLOR(COLOR) "\033[0;" COLOR "m"
| ^~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:269:27: note: in expansion of macro 'LOG_COLOR'
269 | #define LOG_COLOR_W LOG_COLOR(LOG_COLOR_BROWN)
| ^~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:282:37: note: in expansion of macro 'LOG_COLOR_W'
282 | #define LOG_FORMAT(letter, format) LOG_COLOR_ ## letter #letter " (%" PRIu32 ") %s: " format LOG_RESET_COLOR "\n"
| ^~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:411:86: note: in expansion of macro 'LOG_FORMAT'
411 | else if (level==ESP_LOG_WARN ) { esp_log_write(ESP_LOG_WARN, tag, LOG_FORMAT(W, format), esp_log_timestamp(), tag, ##VA_ARGS); } \
| ^~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:432:41: note: in expansion of macro 'ESP_LOG_LEVEL'
432 | if ( LOG_LOCAL_LEVEL >= level ) ESP_LOG_LEVEL(level, tag, format, ##VA_ARGS); \
| ^~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:343:38: note: in expansion of macro 'ESP_LOG_LEVEL_LOCAL'
343 | #define ESP_LOGD( tag, format, ... ) ESP_LOG_LEVEL_LOCAL(ESP_LOG_DEBUG, tag, format, ##VA_ARGS)
| ^~~~~~~~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:5: note: in expansion of macro 'ESP_LOGD'
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:1: error: format '%d' expects argument of type 'int', but argument 7 has type 'int32_t' {aka 'long int'} [-Werror=format=]
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^ ~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:282:59: note: in definition of macro 'LOG_FORMAT'
282 | #define LOG_FORMAT(letter, format) LOG_COLOR_ ## letter #letter " (%" PRIu32 ") %s: " format LOG_RESET_COLOR "\n"
| ^~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:432:41: note: in expansion of macro 'ESP_LOG_LEVEL'
432 | if ( LOG_LOCAL_LEVEL >= level ) ESP_LOG_LEVEL(level, tag, format, ##VA_ARGS); \
| ^~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:343:38: note: in expansion of macro 'ESP_LOG_LEVEL_LOCAL'
343 | #define ESP_LOGD( tag, format, ... ) ESP_LOG_LEVEL_LOCAL(ESP_LOG_DEBUG, tag, format, ##VA_ARGS)
| ^~~~~~~~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:5: note: in expansion of macro 'ESP_LOGD'
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:1: error: format '%d' expects argument of type 'int', but argument 7 has type 'int32_t' {aka 'long int'} [-Werror=format=]
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^ ~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:282:59: note: in definition of macro 'LOG_FORMAT'
282 | #define LOG_FORMAT(letter, format) LOG_COLOR_ ## letter #letter " (%" PRIu32 ") %s: " format LOG_RESET_COLOR "\n"
| ^~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:432:41: note: in expansion of macro 'ESP_LOG_LEVEL'
432 | if ( LOG_LOCAL_LEVEL >= level ) ESP_LOG_LEVEL(level, tag, format, ##VA_ARGS); \
| ^~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:343:38: note: in expansion of macro 'ESP_LOG_LEVEL_LOCAL'
343 | #define ESP_LOGD( tag, format, ... ) ESP_LOG_LEVEL_LOCAL(ESP_LOG_DEBUG, tag, format, ##VA_ARGS)
| ^~~~~~~~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:5: note: in expansion of macro 'ESP_LOGD'
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:265:27: error: format '%d' expects argument of type 'int', but argument 7 has type 'int32_t' {aka 'long int'} [-Werror=format=]
265 | #define LOG_COLOR(COLOR) "\033[0;" COLOR "m"
| ^~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:270:27: note: in expansion of macro 'LOG_COLOR'
270 | #define LOG_COLOR_I LOG_COLOR(LOG_COLOR_GREEN)
| ^~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:282:37: note: in expansion of macro 'LOG_COLOR_I'
282 | #define LOG_FORMAT(letter, format) LOG_COLOR_ ## letter #letter " (%" PRIu32 ") %s: " format LOG_RESET_COLOR "\n"
| ^~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:414:86: note: in expansion of macro 'LOG_FORMAT'
414 | else { esp_log_write(ESP_LOG_INFO, tag, LOG_FORMAT(I, format), esp_log_timestamp(), tag, ##VA_ARGS); } \
| ^~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:432:41: note: in expansion of macro 'ESP_LOG_LEVEL'
432 | if ( LOG_LOCAL_LEVEL >= level ) ESP_LOG_LEVEL(level, tag, format, ##VA_ARGS); \
| ^~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/components/log/include/esp_log.h:343:38: note: in expansion of macro 'ESP_LOG_LEVEL_LOCAL'
343 | #define ESP_LOGD( tag, format, ... ) ESP_LOG_LEVEL_LOCAL(ESP_LOG_DEBUG, tag, format, ##VA_ARGS)
| ^~~~~~~~~~~~~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:67:5: note: in expansion of macro 'ESP_LOGD'
67 | ESP_LOGD(TAG, "Event dispatched from event loop base=%s, event_id=%d", base, event_id);
| ^~~~~~~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c: In function 'app_main':
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:88:10: error: 'esp_mqtt_client_config_t' has no member named 'uri'
88 | .uri = CONFIG_MQTT_HOSTNAME,
| ^~~
H:/Espressif/frameworks/esp-idf-v5.1.1/examples/ipv6_test/main/ipv6_example_main.c:87:41: error: missing braces around initializer [ -Werror=missing-braces]
87 | esp_mqtt_client_config_t mqtt_cfg = {
| ^
cc1.exe: some warnings being treated as errors
[886/895] Performing build step for 'bootloader'
[1/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/lldesc.c.obj
[2/104] Generating project_elf_src_esp32.c
[3/104] Building C object esp-idf/xtensa/CMakeFiles/__idf_xtensa.dir/eri.c.obj
[4/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/dport_access_common.c.obj
[5/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/spi_periph.c.obj
[6/104] Building C object esp-idf/xtensa/CMakeFiles/__idf_xtensa.dir/xt_trax.c.obj
[7/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/interrupts.c.obj
[8/104] Building C object CMakeFiles/bootloader.elf.dir/project_elf_src_esp32.c.obj
[9/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/uart_periph.c.obj
[10/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/gpio_periph.c.obj
[11/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/dport_access.c.obj
[12/104] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/adc_periph.c.obj
