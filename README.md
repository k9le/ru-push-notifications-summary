# Push notifications

  

[\[apple doc\]](https://developer.apple.com/documentation/usernotifications)

  

**Запрос пермишена** [**\[doc\]**](https://developer.apple.com/documentation/usernotifications/asking_permission_to_use_notifications)

Чтобы приложение могло отображать уведомления, у пользователя необходимо запросить разрешение. Это возможно сделать несколькими методами: с помощью обычной всплывашки и с помощью [provisional authorization](https://developer.apple.com/documentation/usernotifications/asking_permission_to_use_notifications#3544375).

Также, перед отправкой локального уведомления, тоже всегда надо проверять пермишены (тк они могут быть изменены в любой момент в настройках приложения). Подробнее в [\[doc\]](https://developer.apple.com/documentation/usernotifications/asking_permission_to_use_notifications)

  

**Действия для нотификаций** [**\[doc\]**](https://developer.apple.com/documentation/usernotifications/declaring_your_actionable_notification_types)

Нотификации бывают двух типов: обычные, которые просто перекидывают пользователя в приложение; и с встроенными действиями. Подробнее о действиях - в [**\[doc\]**](https://developer.apple.com/documentation/usernotifications/declaring_your_actionable_notification_types)

  

**Локальные уведомления** [**\[doc\]**](https://developer.apple.com/documentation/usernotifications/scheduling_a_notification_locally_from_your_app)

Локальные уведомления позволяют сообщить пользователю о каких-либо событиях или завершении процессов. Уведомление может быть запланировано по времени или локации. Если в момент нотификации приложение не запущено или в бэкграунде - показ регулируется системой. Если приложение запущено - система доставляет уведомление в приложение для управления.

Локальное уведомление может быть [отменено](https://developer.apple.com/documentation/usernotifications/scheduling_a_notification_locally_from_your_app#2980216) еще до выполнения.

  

**Remote Notifications** [**\[doc\]**](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server)

Общая схема работы механизма пушей в [\[doc\]](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server).

Для конфигурации сервера, который будет отправлять пуши, необходимо защищенное соединение с APNs. Для этого используются два способа:

*   Token-based trust with APNs [\[doc\]](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns)
*   Certificate-based trust with APNs [\[doc\]](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns)

  

Remote push имеет JSON-payload, который содержит всю информацию о пуше. Максимальный размер пейлоада - 4 кб для обычных пушей, 5 кб для VoIP пушей. 

В пейлоаде могут быть как стандартные поля (с заголовком, телом пуша, категорией, звуком и тд, [полный список](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/generating_a_remote_notification#2943360)), так и нестандартные, которые используются уже при обработке пуша приложением. [\[подробности\]](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/generating_a_remote_notification) [\[локализация сообщений\]](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/generating_a_remote_notification#2948651)

Чтобы начать получать пуши в конкретное приложение на концертном девайсе, надо получить уникальный токен и передать его серверу, который будет отправлять эти пуши. [\[doc\]](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns)

Обработка пушей в случае, если приложение в форграунде [\[doc\]](https://developer.apple.com/documentation/usernotifications/handling_notifications_and_notification-related_actions#2942082)

Модификация контента пуша [\[doc\]](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications)

  

Кастомизация внешнего вида баннеров для локальных и remote уведомлений [\[doc\]](https://developer.apple.com/documentation/usernotificationsui)
