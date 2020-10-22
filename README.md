# Clain_case
-- Описание задания

Мы предлагаем Вам попробовать свои силы в решении небольшой задачки. Как известно, блокчейн биткоина хранит все когда-либо используемые адреса и транзакции между ними. Несмотря на кажущуюся анонимность данной криптовалюты, есть широкоизвестные методы, которые позволяют связать множество адресов, предполагая что они принадлежат одному и тому же владельцу (это может быть человек или компания). Так как все транзакции между адресами прозрачны, мы можем видеть сколько денег ушло от одного владельца к другому (это называется сash flow). Мы предоставляем такую услугу нашим клиентам и предлагаем Вам посчитать сash flow между двумя кластерами адресов.

-- Необходимые предметные знания

Транзакция биткоина представляет собой набор входных и выходных адресов, а также указание сколько каждый адрес вносит биткоинов в данную транзакцию (для входных) или забирает из транзакции (для выходных адресов). Стоит заметить, что ничего не известно о том, сколько биткоинов переправляет конкретный входной адрес на любой другой из выходных. Также часть средств из суммы входов уходит в качестве сбора (fee) для майнеров при включении транзакции в новый блок. Мы можем найти fee (fee >= 0) как разницу между суммой входов и суммой выходов транзакции.

-- Описание структуры файлов

address_clust.csv включает в себя набор адресов из 1 и 2 кластера с указанием данного кластера.
address_id - адрес
cluster_id - кластер

address_stats.csv включает в себя описание всех транзакций с участием в них адресов из файла address_clust.csv.
id - просто id записи
address_id - адрес
transaction_id - транзакция
received - сумма в сатоши (1 биткоин = 10^8 сатоши) полученная данным адресом в данной транзакции
sent - сумма в сатоши отправленная данным адресом в данной транзакции

Помимо имеющихся в address_clust.csv адресов, файл address_stats.csv содержит еще дополнительные адреса, являющиеся внешними по отношению к кластеру 1 и 2, можете сопоставить им всем кластер 0.

-- Задача

Сколько биткоинов отправил кластер 1 в кластер 2 и сколько кластер 2 отправил в кластер 1?
Доп. вопросы:
Сколько биткоинов отправил кластер 1 в кластер 0 и сколько кластер 0 отправил в кластер 1?
Сколько биткоинов отправил кластер 2 в кластер 0 и сколько кластер 0 отправил в кластер 2?
Сколько биткоинов потратил кластер 1 и кластер 2 на fee?
