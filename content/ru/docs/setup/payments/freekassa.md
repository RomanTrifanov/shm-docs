
---
title: FreeKassa
weight: 3
---

## Настройка платежной системы FreeKassa

* Зарегистрируйтесь в сервисе FreeKassa  (https://freekassa.com/)
* Откройте страницу "Настройки" (https://merchant.freekassa.com/settings)
* Сохраните в [конфиг]({{< ref "/docs/api/config" >}}) SHM следующие данные:
```yaml
{
  "pay_systems": {
    "freekassa": {
      "name": "FreeKassa"
      "show_for_client": true
      "merchant_id": ID_магазина_сверху_страницы
      "secret_word_1": СЕКРЕТНОЕ_СЛОВО_1
      "secret_word_2": СЕКРЕТНОЕ_СЛОВО_2
    }
  }
}
```
* В разделе "Ссылки и методы" укажите `URL ОПОВЕЩЕНИЯ` и `МЕТОД` `POST`:

  `https://admin.ВАШ-ДОМЕН/shm/pay_systems/freekassa.cgi`

* Нажмите кнопку "ПРОВЕРИТЬ СТАТУС". Вы должны увидеть статус `200`, а в Админке SHM, в платежах, Вы увидите тестовый платеж.
* Остальные поля заполните по вашему усмотрению


### Пример ссылки для создания платежа:

`https://ВАШ_ДОМЕН/shm/pay_systems/freekassa.cgi?action=create&amount=123`

