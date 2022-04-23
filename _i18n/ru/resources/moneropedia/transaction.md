---
summary: 'Криптографически подписанный контейнер, в котором содержится подробная информация по передаче Monero получателю (или получателям).'
terms: ["transaction", "transactions", "транзакций", "транзакции", "транзакция"]
---

{% include disclaimer.html translated="yes" translationOutdated="no" %}

### Основная информация

Криптографически подписанный контейнер, в котором содержится подробная
информация по передаче Monero получателю (или получателям).

Среди параметров транзакции содержатся один или несколько адресов получателя
с соответствующими суммами средств, а также параметр размера кольца, который
указывает количество выходов, связанных с транзакцией. Чем больше выходов
используется, тем выше уровень защиты. Но это имеет свою цену. Так как при
включении большего количества выходов транзакция становится больше, растёт и
размер комиссии за проведение транзакции.

Можно создать офлайн транзакцию, что даёт дополнительные преимущества с
точки зрения анонимности.

Транзакция может быть уникально идентифицирована. Для этого используется
опциональный идентификатор транзакции (Transaction ID), который, как
правило, представляет собой 32-байтную строку (64 шестнадцатеричных
символа).

### Углублённая информация

При проведении каждой транзакции используется два ключа: публичный
@ключ-траты и публичный @ключ-просмотра. Адрес назначения для выхода
транзакции фактически является одноразовым публичным ключом, который
вычисляется на основе этих двух ключей.

Когда кошелёк сканирует входящие транзакции, то каждая транзакция
сканируется на предмет того, направлена ли она именно вам. Для этого
необходимы только ваш приватный ключ просмотра и ваш публичный ключ
траты. Такая проверка проводится неизменно, и её нельзя подделать. Вы не
можете принять транзакции и идентифицировать их, не имея соответствующего
приватного ключа просмотра.

Чтобы потратить средства, вам понадобится вычислить одноразовый приватный
ключ траты для данного конкретного выхода. Это практически всегда делается
автоматически программным обеспечением кошелька Monero.