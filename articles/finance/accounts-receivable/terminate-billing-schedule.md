---
title: Kończenie harmonogramów rozliczania
description: W tym temacie wyjaśniono, jak zakończyć fakturowanie harmonogramów i wierszy harmonogramu fakturowania w ramach fakturowania subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e823ce950d6a4687dc7cda14e06bffdbb4f37f7e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690984"
---
# <a name="terminate-billing-schedules"></a>Kończenie harmonogramów rozliczania

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak zakończyć fakturowanie harmonogramów i wierszy harmonogramu fakturowania w ramach fakturowania subskrypcji. Po zakończeniu fakturowania harmonogram musi mieć stan **Aktywny**. Nie można mieć stanu **Wstrzymano**. Podobnie, gdy kończysz wiersz harmonogramu rozliczeń, musi on mieć stan **Aktywny**. Sekcja nagłówka harmonogramu fakturowania nie ma wpływu na zakończenie wiersza harmonogramu fakturowania.

Aby zakończyć fakturowanie zgodnie z harmonogramem lub wierszem harmonogramu fakturowania, przejdź do jednego z następujących miejsc:

- Strona **listy wszystkich/aktywnych harmonogramów** fakturowania
- Określony harmonogram fakturowania na stronie **Wszystkie harmonogramy fakturowania**
- Określony wiersz harmonogram fakturowania na stronie **Wszystkie harmonogramy fakturowania**

> [!NOTE]
> Aby jednocześnie zakończyć kilka harmonogramów fakturowania, należy użyć strony przetwarzania **zakończenia masowego**.

## <a name="terminate-a-billing-schedule-or-line"></a>Zakończ harmonogram lub linię rozliczeniową

Aby zakończyć harmonogram rozliczeń lub wiersz harmonogramu rozliczeń, wykonaj następujące kroki.

1. Wybierz harmonogram fakturowania lub wiersz harmonogramu fakturowania, a następnie **zakończ**. 
2. Ustaw pola **Data zakończenia**, **Typ zakończenia** i **Kod przyczyny**.
3. Ustaw w polu **Opcja kredytu** wartość **Kredyt przy wydaniu**.
4. Wybierz opcję **Zakończ**.

Stan harmonogramu fakturowania zmienia się na podstawie wybranego typu zakończenia zatrudnienia. Jeśli jako typ zakończenia wybrano opcję **Pozostałe weksla**, stan wszystkich wierszy w harmonogramie fakturowania będzie następujący: **Ostatnia faktura**. Stan harmonogramu fakturowania pozostaje **aktywny** do czasu przetworzenia ostatniej faktury. Po przetworzeniu ostatniej faktury stan jest aktualizowany na **Przerwane**. Jeśli jako typ zakończenia wybrano **Dostosuj harmonogram**, stan harmonogramu rozliczeń zostanie natychmiast zaktualizowany do **Przerwane**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Zakończ harmonogram fakturowania lub wiersz i zastosuj zwrot

Aby zakończyć harmonogram rozliczeń lub wiersz harmonogramu rozliczeń i zastosować zwrot pieniędzy, wykonaj następujące kroki.

1. Wybierz harmonogram fakturowania lub wiersz harmonogramu fakturowania, a następnie **zakończ**.
2. Ustaw pola **Data zakończenia**, **Typ zakończenia**, **Kod przyczyny** i **Opcja kredytu**.
3. Wybierz opcję **Zakończ ze zwrotem**. Zostanie **wyświetlona strona przetwarzania** zakończenia zatrudnienia masowego, która jest odfiltrowana w taki sposób, aby przedstawiała harmonogram fakturowania.
4. Wybierz opcję **Wyświetl podgląd**, aby wyświetlić wiersze harmonogramu rozliczeń, a następnie wybierz **Przetwarzaj**.

Po przetworzeniu kredytu otwórz stronę **Podgląd szczegółów fakturowania**, aby przejrzeć kredyt zastosowany do harmonogramu fakturowania. Jeśli kwota kredytu jest większa niż 0 (zero), wszystkie przyszłe wiersze niepodpisane są usuwane i zastępowane wierszy szczegółów fakturowania, które pokazują ujemne kwoty kredytu zastosowane w harmonogramie fakturowania.

### <a name="view-example"></a>Wyświetl przykład

Harmonogram fakturowania zawiera następujące informacje:

- Data rozpoczęcia to 1 stycznia 2020.
- Data końcowa to 31 grudnia 2020.
- Kwota okresu fakturowania wynosi 100,00 na miesiąc.
- Utworzono faktury dla okresów fakturowania od stycznia do lipca.
- Data zakończenia umowy to 15 czerwca 2020.

Podczas przetwarzania korekty kredytu wszystkie przyszłe okresy fakturowania (od sierpnia do grudnia) są usuwane ze strony **Przeglądanie szczegółów fakturowania**. Wiersz korekty kredytu jest dodawany po lipcowym okresie rozliczeniowym:

- 16 czerwca –31 lipca z kwotą kredytu 150,00 zł

Jeśli używana jest funkcja nierozliczonych przychodów, strona **Kontrola wpisów do dziennika przychodów nierozliczonych** jest aktualizowana wpisem o zakończeniu.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Zakończ harmonogram lub linię rozliczeniową bez zastosowania kredytu

Aby zakończyć harmonogram rozliczeń lub wiersz harmonogramu rozliczeń bez zastosowania kredytu, wykonaj następujące kroki.

1. Wybierz harmonogram fakturowania lub wiersz harmonogramu fakturowania, a następnie **zakończ**.
2. Ustaw pole **Data zakończenia**.
3. W polu **Typ zakończenia** ustaw wartość **Brak korekty** Pole **Opcja kredytu** jest automatycznie ustawiane na **Brak kredytu**.
3. Ustaw pole **Kod przyczyny**.
4. W polu **notatki zakończenia** wprowadź wszelkie dodatkowe notatki, które są wymagane.
5. Wybierz opcję **Zakończ**. 

Podczas przetwarzania zakończenia zatrudnienia wszystkie wiersze szczegółów fakturowania po dacie zakończenia są usuwane. (Te wiersze zawierają wiersz zawierający datę zakończenia zatrudnienia) Nie można utworzyć faktur dla wierszy przerwanych. Jeśli zakończenie zostanie usunięte, wszystkie zakończone linie zostaną ponownie dodane do strony **Wyświetl szczegóły płatności** i staną się dostępne do fakturowania.

## <a name="fields"></a>Pola

Strona **Wyświetl szczegóły fakturowania** zawiera następujące pola.

| Pole | Opis |
|-------|-------------| 
| Data zakończenia | Wybierz datę, kiedy chcesz zakończyć harmonogram rozliczeń lub wiersz harmonogramu rozliczeń. |
| Typ wypowiedzenia | <p>Wybierz rodzaj zakończenia:</p><ul><li>**Dostosuj harmonogram** — umożliwia odcięcie okresów fakturowania dla wiersza na dzień zakończenia zatrudnienia oraz zmianę stanu wiersza na **Ostatnia faktura** Jeśli istnieje harmonogram odroczeń dla pozycji w wierszu, jest on korygowany przez cofanie kwoty, która nie musi już być rozpoznawana. Jeśli data rozpoczęcia fakturowania jest późniejsza niż data zakończenia, pozostałe okresy fakturowania są usuwane.</li><li>**Pozostałe do rozliczenia** — Dodaj pozostałą kwotę za okres fakturowania do okresu zakończenia zatrudnienia i zmień stan wiersza na **Ostatnia faktura** Jeśli istnieje harmonogram odroczenia dla pozycji, data zakończenia odroczenia jest aktualizowana. Jeśli data rozpoczęcia fakturowania jest późniejsza niż data zakończenia, do okresu fakturowania jest dodawana łączna kwota wszystkich pozostałych okresów fakturowania, a pozostałe okresy fakturowania są usuwane.</li><li>**Brak korekty** — należy zakończyć okresy fakturowania dla wiersza w określonej dacie zakończenia zatrudnienia. Nie dokonano żadnych korekt. Po wybraniu tego typu zakończenia w polu **Opcja kredytu** jest ustawiona wartość **Bez kredytu**, a w polu **Dostosuj dzienne** jest ustawiona wartość **Nie**. Oba pola stają się następnie tylko do odczytu i nie można ich zmienić.</li></ul> |
| Opcja kredytu | <p>Umożliwia wybranie sposobu stosowania kredytu w przypadku zakończenia wiersza harmonogramu fakturowania:</p><ul><li>**Korekta kredytu** – Umożliwia utworzenie korekty kredytu dla harmonogramu fakturowania po zakończeniu wiersza. Korekta kredytu pojawi się w przyszłym okresie fakturowania dla harmonogramu fakturowania. Korekta automatycznie koryguje również kwotę faktury dla następnego okresu fakturowania do czasu zastosowania kredytu do harmonogramu fakturowania.</li><li>**Wystaw kredyt** – Utwórz notę kredytową po zakończeniu harmonogramu rozliczeń lub wiersza harmonogramu rozliczeń.</li><li>**Bez kredytu** – Nie twórz korekty kredytowej ani noty kredytowej, gdy harmonogram rozliczeń lub wiersz harmonogramu rozliczeń zostanie zakończony. Ta opcja jest dostępna tylko po zakończeniu pracy z typem **Brak korekty** w celu zakończenia fakturowania.</li></ul><p>Opcja domyślna znajduje się na stronie **Parametry fakturowania umowy cyklicznej**.</p> |
| Kod przyczyny | Wybierz kod przyczyny wypowiedzenia. |
| Opis przyczyny | Opis kodu przyczyny. |
| Uwagi dotyczące wypowiedzenia | Wprowadź wszelkie uwagi dotyczące rozwiązania umowy. |

<!--## Additional information-->
