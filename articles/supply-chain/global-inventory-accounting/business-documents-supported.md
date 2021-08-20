---
title: Dokumenty biznesowe obsługiwane przez Globalne księgowanie zapasów
description: W tym temacie wymieniono dokumenty biznesowe, które są obsługiwane przez program Globalne księgowanie zapasów. Zawiera również szczegółowy przykład dla dokumentów zamówień zakupu.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cdb2d119e9b49887bb66fa737f97c3d91e5b793ceea1b2389072a02b5c463ba9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726877"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Dokumenty biznesowe obsługiwane przez Globalne księgowanie zapasów

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Po pełnym skonfigurowaniu dodatku Globalne księgowanie zapasów jest on gotowy do przetwarzania dokumentów związanych z inwentaryzacją, które są wprowadzane w systemie Microsoft Dynamics 365 Supply Chain Management.

## <a name="supported-business-documents"></a>Obsługiwane dokumenty biznesowe

Istnieją dwa typy akcji biznesowych:

- **Dokumenty, które mają arkusza** – Dokumenty te obejmują paragon, fakturę zakupu, dokument dostawy i fakturę sprzedaży.
- **Dokumenty, które nie mają arkusza** – Dokumenty te obejmują dokumenty dotyczące liczenia, przemieszczania i korekty stanów magazynowych.

W dalszej części tego tematu, zamówienia zakupu zostaną użyte jako przykład ilustrujący ten proces.

W poniższej tabeli wymieniono dokumenty, które obsługuje bieżąca wersja.

| Typ dokumentu       | Wydruk pokwitowania        |
|--------------------|-----------------|
| Zamówienie zakupu     | Dokument przyjęcia produktów |
| Zamówienie zakupu     | Faktura VAT         |
| Zamówienie sprzedaży        | Dokument dostawy    |
| Zamówienie sprzedaży        | Faktura VAT         |
| Arkusze magazynowe | Transakcje        |
| Arkusze magazynowe | Korekta      |
| Arkusze magazynowe | Inwentaryzacja        |
| Arkusze magazynowe | Przeniesienie        |
| Zamówienie przeniesienia     | Wysyłka        |
| Zamówienie przeniesienia     | Pobierz         |

> [!IMPORTANT]
> Globalne księgowanie zapasów asynchronicznie przetwarza dokumenty wprowadzone w Supply Chain Management. Nie będą wyświetlane komunikaty o błędach dla problematycznych dokumentów.

## <a name="example-purchase-order"></a>Przykład: Zamówienia zakupu

### <a name="product-receipt"></a>Dokument przyjęcia produktów

Zaksięguj potwierdzenie odbioru produktu w zwykły sposób. Na stronie **Wszystkie zamówienia zakupu** wybierz zamówienie zakupu, a następnie na pasku akcji, na karcie **Odbiór** wybierz **Przyjmowanie produktów** , aby otworzyć stronę **Arkusz przyjmowania produktów**. Dla każdej linii generowane jest zdarzenie operacyjne oraz zdarzenie globalnego księgowania zapasów. Dlatego należy wybrać zakładkę **Wiersze**, a następnie wybrać **Zapasy \> Zdarzenia i pomiary**, aby otworzyć stronę **Zdarzenia i pomiary**.

Globalne księgowanie zapasów to system księgowania oparty na zdarzeniach i miarach. W siatce wiersza miary na stronie **Zdarzenia i miary** jest wyświetlona lista miar. Każda miara ma listę wymiarów.

Dla każdego zdarzenia operacyjnego istnieją dwa rodzaje pomiarów:

- **Pomiary operacyjne** – Pomiary te opisują dokumenty biznesowe w sposób ogólny. Jedną miarą jest ilość produktu przy użyciu jednostka miary która jest używana w dokumencie. Istnieją również miary, które wpływają na wartość zapasów, takie jak cena rozszerzona, rabat, procent rabatu i opłata za linię.
- **Pomiary księgowe zasobów** – są to pomiary z punktu widzenia ewidencji zapasów. Opisują one wpływ dokumentu na ewidencję w jednostce miary ewidencji. Jeśli istnieje wiele rejestracji zapasów, istnieje wiele wierszy pomiarów księgowych zasobów.

Wymiary są zorganizowane w następujący sposób:

- **Dualność** – Dualność opisuje podmioty, które uczestniczą w zdarzeniach gospodarczych. W przypadku zewnętrznych dokumentów biznesowych wymiary pierwotne opisują podmiot prawny, w którym dokument jest wprowadzany, natomiast wymiary dualne opisują sprzedawcę, klienta itd. Dla wewnętrznych dokumentów biznesowych (np. poleceń przelewu) podwójne wymiary opisują magazyn kontrahenta.
- **Typ wymiaru** — typy wymiarów kategoryzują wymiary.
- **Wymiar** – Nazwa wymiaru w module.
- **Wartość wymiaru** – Wartość wymiaru w module.

### <a name="global-inventory-accounting-event"></a>Zdarzenie księgowania globalnych zapasów

Globalne księgowanie zapasów przyjmuje zdarzenia operacyjne i pomiary jako dane wejściowe. Następnie wykonuje odpowiednie księgowania dla każdej powiązanej księgi, w oparciu o dołączoną walutę i konwencję. Można wybrać **Globalne księgowanie zapasów – wydarzenia i wymiary**, aby wyświetlić zdarzenie księgowania zapasów globalnych. Zdarzenie księgowe w magazynie globalnym opiera się na tej samej metodologii co zdarzenia operacyjne, ale wykorzystuje inne pomiary. Istnieją trzy główne rodzaje pomiarów: ilość kosztu produktu, koszt produktu i odchylenie.

Konta ksiąg pomocniczych są wykorzystywane do dalszej klasyfikacji pomiarów. Może być wiele ksiąg. Te księgi są połączone z podmiotem prawnym, w którym jest wprowadzany dokument. Zdarzenia i miary dla poszczególnych ksiąg można wyświetlić, zmieniając wartość pola **Księga**.

### <a name="cost-element"></a>Składnik kosztu

Na podstawie polityki elementów kosztowych, która jest dołączona do księgi, system przypisuje element kosztowy do każdego rozliczanego pomiaru zdarzenia operacyjnego, które ma wpływ na koszt zapasów. Pomiary te obejmują cenę rozszerzoną, rabat, procent rabatu i opłatę liniową.

### <a name="measurement-line-details"></a>Szczegóły wiersza miary

Na karcie **Przegląd** pokazano szczegóły dołączonych zasad. Wymiary obiektu kosztowego pokazują obiekt kosztowy w oparciu o politykę obiektu kosztowego. Specyficzne wymiary identyfikacyjne pokazują numer partii, jeśli założeniem przepływu kosztów jest *Szczególne - Partia*.

### <a name="purchase-invoice"></a>Faktura zakupu

Zaksięguj fakturę w zwykły sposób. Następnie na pasku akcji, na karcie **Faktura**, w grupie **Dzienniki** wybierz **Faktura**, aby otworzyć dziennik faktur. Dla każdej linii generowane jest zdarzenie operacyjne oraz zdarzenie globalnego księgowania zapasów. Dlatego należy wybrać zakładkę **Wiersze**, a następnie wybrać **Zapasy \> Zdarzenia i pomiary**, aby otworzyć stronę **Zdarzenia i pomiary**. Na stronie **Zdarzenia i miary** jest przedstawiany ten sam typ miary. Ponieważ jednak na stronie widnieje inna rola środka i inny modyfikator środka, wpływ na agenta (osobę prawną) jest inny.

Wybierz **Globalne księgowanie zapasów – wydarzenia i wymiary**, aby wyświetlić zdarzenie księgowania zapasów globalnych. Ilość i koszt zapasów wypływają teraz z konta księgi pomocniczej *Otrzymane towary niezafakturowane* na konto księgi pomocniczej *Koszt zakupionych towarów*.
