---
title: Automatyczne propozycje płatności dla dostawcy
description: W tym temacie wyjaśniono, w jaki sposób organizacje płacące dostawcom w harmonogramie cyklicznym mogą zautomatyzować proces generowania propozycji płatności dla dostawcy.
author: kweekley
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: a1e3305bff99fa39240176ac9fc7aaee84b98e6c
ms.sourcegitcommit: be51e892003778e71b67fb409a8e16965c89b5ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2020
ms.locfileid: "3618418"
---
# <a name="automate-vendor-payment-proposals"></a>Automatyczne propozycje płatności dla dostawcy

[!include [banner](../includes/banner.md)]

Organizacje płacące dostawcom w harmonogramie cyklicznym mogą teraz zautomatyzować proces generowania propozycji płatności dla dostawcy. Automatyzacja propozycji płatności dla dostawcy definiują następujące informacje:

- Kiedy są przesyłane propozycje płatności
- Jakie kryteria służą do wybierania faktur, które powinny zostać zaopłacone
- W jakim arkuszu płatności dostawcy będą zapisywane wynikające płatności

Automatyzacja propozycji płatności nie księguje automatycznie płatności. Można więc nadal korzystać z dowolnych procesów sprawdzania poprawności i przepływu pracy, które są obecnie używane do zatwierdzania tworzonych płatności.

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Definiowanie wystąpienia propozycji płatności dla dostawcy

For example, if an occurrence is for check payments on Monday, you can define it so that it runsAutomatyzacja propozycji płatności od dostawcy korzysta ze struktury Automatyzacji procesów. W różnych procesach biznesowych te struktury są używane do definiowania cyklu wybranego procesu. W przypadku propozycji płatności dla dostawcy automatyzacja może być dostępna w **Rozrachunki z dostawcami \> Ustawienia płatności \> Automatyzacja procesu**.

Najpierw należy skorzystać z opcji automatyzacji **Utwórz nowy proces** i wybrać opcję **Propozycja płatności dostawcy**. Kreator przeprowadzi Cię przez proces konfigurowania propozycji płatności dostawcy.

## <a name="general-page"></a>Strona ogólna

Na stronie **Ogólne** kreatora wprowadź nazwę tworzonej propozycji płatności dostawcy. Na przykład, jeśli wszyscy dostawcy krajowi zostaną zapłacone za pomocą czeku w poniedziałek, należy wprowadzić nazwę opisową, np **Krajowe\_Czek**. Wprowadzona nazwa jest wyświetlana w widoku tygodniowym automatyzacji procesu w obszarze roboczym **Płatności dla dostawców**.

Następnie należy zdefiniować właściciela tworzonego arkusza płatności. Właścicielem jest zazwyczaj pracownik ds. rozrachunków z dostawcami (AP), który jest odpowiedzialny za arkusz płatności po jego utworzeniu

Pozostałe ustawienia na stronie są ogólne i służą do definiowania wzorca występowania dla tej wersji propozycji płatności dostawcy. Jeśli na przykład wystąpienie jest przeznaczone do sprawdzania płatności w poniedziałek, można je zdefiniować w taki sposób, aby było wykonywane co tydzień, a w chwili uruchamiania będzie można wybrać poniedziałek jako dzień tygodnia. Można również wprowadzić wcześniej zaplanowany czas, na przykład godz. 2:00, tak aby automatyzacja procesu była zakończona przed rozpoczęciem następnego dnia roboczego.

Ważne jest, aby rozumieć, że użytkownik korzysta z kreatora w celu określenia, kiedy jest przetwarzana propozycja płatności dostawcy. Nie definiuje się, kiedy płatności dostawcy są generowane, drukowane i księgowane. W widoku tygodniowym automatyzacja procesu dla propozycji płatności dostawcy pojawi się w dniach wybranych we wzorcu wystąpienia.

Aby uzyskać więcej informacji o innych polach na stronie **Ogólne**, zapoznaj się z dokumentacją automatyzacji procesu.

## <a name="vendor-payment-proposal-page"></a>Strona propozycji płatności dla dostawcy

Następną stroną kreatora jest strona **Propozycje płatności dostawcy**. Służy do definiowania kryteriów wyboru faktur od dostawców, które powinny zostać zaopłacone. Na ogół te same opcje można znaleźć w propozycji płatności w arkuszu płatności dostawcy. Występują jednak pewne wyjątki. Na przykład wszystkie daty na tej stronie muszą być zdefiniowane jako względne daty, ponieważ data propozycji płatności zmienia się przy każdym uruchomieniu propozycji.

### <a name="journal-name"></a>Nazwa arkusza

Pole **Nazwa arkusza** definiuje nazwę arkusza, w którym są tworzone płatności dostawcy. Wyniki automatyzacji propozycji płatności dostawcy spowodują utworzenie płatności w zdefiniowanym arkuszu, ale arkusz nie zostanie zaksięgowany.

### <a name="from-date-and-to-date"></a>Data „Od” i data „do”

Zamiast definiować datę „od” i „do”, aby wybrać faktury na podstawie daty należności lub rabatu gotówkowego, należy użyć opcji **Zdefiniuj kryteria do daty** i pola **Korekta liczby dni dla Do daty**, aby zdefiniować datę końcową. Nie istnieje pojęcie daty „od” w automatyzacjach propozycji płatności.

Domyślnie opcja **Zdefiniuj kryteria do daty** jest ustawiona na wartość **Nie**. Jeśli zostanie użyta ta wartość domyślna, proces wybierze wszystkie faktury dla płatności, gdy proces zostanie uruchomiony, ponieważ nie zostanie zdefiniowana data „do”.

Jeśli ustawienie opcji **Zdefiniuj kryteria do daty** ma wartość **Tak**, należy skorzystać z **Korekta liczby dni dla Do daty**, aby zdefiniować datę wybrania faktur jako określoną liczbę dni przed uruchomieniem procesu lub po nim. Liczba może być dodatnia, ujemna lub 0 (zero). System będzie wypłacać faktury, w których daty należności lub rabaty gotówkowe będą określoną liczbę dni przed lub po dacie uruchomienia procesu. Na przykład dla wszystkich faktur, które są należne w piątek lub przed piątkiem, seria płatności tworzy płatności dla wszystkich dostawców przez sprawdzenie w środę. W takim przypadku należy określić wartość pola **Korekta liczby dni dla Do daty** na **2**. Jeśli wystąpienie propozycji płatności jest wykonywane w środę, 25 marca, wszystkie faktury, które mają datę płatności lub datę rabatu gotówkowego w dniu 27 marca lub wcześniej, zostaną wybrane do zapłaty.

### <a name="minimum-payment-date"></a>Minimalna data płatności

Minimalna data płatności określa najwcześniejszą datę, która jest używana podczas tworzenia płatności. Należy najpierw skonfigurować opcję **Zdefiniuj kryterium minimalnej daty płatności** na **Tak**. To ustawienie umożliwia użycie funkcji minimalnej daty płatności. Jeśli ta opcja jest ustawiona na **Tak**, użyj pola **Korekta liczby dni dla minimalnej daty płatności**, aby zdefiniować minimalną datę płatności jako określoną liczbę dni przed lub po dacie uruchomienia procesu. Liczba może być dodatnia, ujemna lub 0 (zero). Na przykład seria płatności generuje płatności w środę, aby uwzględnić wszystkie płatności o minimalnej dacie płatności w poprzedzający poniedziałek. W takim przypadku należy określić wartość pola **Korekta liczby dni dla minimalnej daty płatności** na **-2**.

Oto przykład, który pokazuje, jak pola dla daty „do” i minimalnej daty płatności działają razem. Automatyzacja propozycji płatności jest skonfigurowana tak, aby była uruchamiana w środę. Wartość pola **Korekta liczby dni dla Do daty** jest ustawiana na **1** w celu zdefiniowania daty „do” na podstawie terminu płatności. Należy określić wartość pola **Korekta liczby dni dla minimalnej daty płatności** na **-2**. Jeśli automatyzacja procesu płatności rozpocznie się w środę, 25 marca, wszystkie faktury należne 26 marca lub wcześniej zostaną uwzględnione w propozycji płatności. Propozycje płatności zostaną wygenerowane w następujący sposób:

- Wszystkie faktury, które są należne 23 marca lub wcześniej, będą miały datę płatności 23 marca.
- Faktury, które są należne 24 marca, będą miały datę płatności 24 marca.
- Faktury, które są należne 25 marca, będą miały datę płatności 25 marca.
- Faktury, które są należne 26 marca, będą miały datę płatności 26 marca.

### <a name="summarized-payment-date"></a>Data sumarycznej płatności

Data sumarycznej płatności jest używana tylko wtedy, gdy pole **Okres** jest ustawione na **Razem** dla metody płatności faktur. Jeśli pole **Okres** jest ustawione na **Razem** dla twoich metod płatności, musisz ustawić opcję **Zdefiniuj kryterium sumarycznej daty płatności** opcję na **Tak**. Jeśli ta opcja jest ustawiona na **Tak**, użyj pola **Korekta liczby dni dla sumarycznej daty płatności**, aby zdefiniować sumaryczną datę płatności jako określoną liczbę dni przed lub po dacie uruchomienia procesu. Liczba może być dodatnia, ujemna lub 0 (zero). Na przykład seria generuje płatności w środę, a firma chce utworzyć sumaryczną płatność w środę. W takim przypadku należy określić wartość pola **Korekta liczby dni dla sumarycznej daty płatności** na **0**.

### <a name="records-to-include"></a>Rekordy do uwzględnienia

W dalszym ciągu można zdefiniować opcje filtrowania dla propozycji płatności. Jeśli filtr jest zdefiniowany, kryteria filtru nie są wyświetlane na stronie kreatora. Można je jednak przejrzeć, ponownie otwierając filtr.

Pozostałe pola propozycji działają tak samo, jak w ramach propozycji płatności w arkuszu płatności dostawcy. Aby uzyskać informacje o innych polach, zapoznaj się z tematem [Tworzenie płatności dostawcy za pomocą propozycji płatności](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Niektóre pola specyficzne dla kraju/regionu i niektóre pola sektorów publicznych nie są jeszcze dostępne w automatyzacjach propozycji płatności dostawcy.

Zalecamy, aby ocenić, czy automatyzacja będzie korzystna dla danej organizacji, zgodnie z wymaganiami użytkownika.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>Umożliwia wyświetlenie wyników automatyzacji propozycji płatności dostawcy

Po utworzeniu serii automatyzacji propozycji płatności dostawcy wystąpienia każdej płatności będą wyświetlane w widoku tygodniowym automatyzacji procesu. W przypadku płatności dostawcy widok tygodniowy automatyzacji procesu został dodany do obszaru roboczego **Płatności dla dostawców** i strony **Automatyzacja procesu**.

[![Widok tygodniowy automatyzacji procesu w obszarze roboczym Płatności dla dostawców](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

Widok tygodniowy automatyzacji procesu w obszarze roboczym **Płatności dla dostawców** pokazuje tylko automatyzację propozycji płatności dostawcy. Pokazuje wszystkie wystąpienia płatności w bieżącym tygodniu dla wszystkich firm, do których zalogowany użytkownik ma uprawnienia bezpieczeństwa. Jeśli na przykład pracownik jest odpowiedzialny za rozrachunki z dostawcami w firmach USMF i USSI, będzie widział wystąpienia automatyzacji propozycji płatności dostawcy dla tych dwóch firm, ale nie dla innych firm.

[![Widok tygodniowy automatyzacji procesu dla firm USMF i USSI](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Każde wystąpienie pokazuje firmę, w której arkusz płatności został lub zostanie utworzony. Jeśli płatności są tworzone za pomocą płatności scentralizowanych, wyświetlana jest firma, w której będą tworzone płatności. Wystąpienie niekoniecznie pokazuje, które faktury firmy będą opłacane.

Nazwa każdego wystąpienia jest również wyświetlana w celu identyfikacji propozycji płatności.

Ponadto wyświetlany jest stan każdego wystąpienia. Wykorzystywane są następujące stany:

- **Zaplanowane** — propozycja płatności jest zaplanowana, ale nie została jeszcze uruchomiona.
- **Błąd** — została uruchomiona propozycja płatności, ale wystąpił błąd. Te błędy można wyświetlić, wybierając przycisk **Wyświetl wyniki**.
- **Zakończono** — propozycja płatności została pomyślnie uruchomiona. Te płatności można wyświetlić, wybierając łącze **Wyświetl płatności**. To łącze powoduje otwarcie arkusza płatności utworzonego przez wystąpienie.

Po utworzeniu płatności można wyświetlić kwoty płatności w arkuszu. Kwoty są wyświetlane w walutach transakcji. Jeśli na przykład arkusz płatności zawiera płatności w dolarach amerykańskich i kanadyjskich, wyświetlane są sumy płatności dla każdej waluty. 

Arkusz płatności można usunąć po jego utworzeniu za pośrednictwem automatyzacji procesu. Jeśli płatność zostanie całkowicie usunięta, wystąpią następujące zdarzenia:

- Stan automatyzacji procesu dla tego tygodnia pozostanie **Zakończony**.
- W procesie usuwane są sumy płatności, a łącze **Wyświetl płatności** jest zastępowane przyciskiem **Wyświetl wyniki**.
- Po wyświetleniu wyników zostanie wyświetlony komunikat informujący o usunięciu oryginalnego arkusza.

Po usunięciu płatności faktury zostaną ponownie otwarte dla płatności. Następnie można utworzyć nowe wystąpienie, aby ponownie zapłacić faktury.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Edytuj automatyzację propozycji płatności od dostawcy

Struktura automatyzacji procesów umożliwia edytowanie płatności, serii i wystąpień utworzonych dla propozycji płatności. Serie można edytować na stronie **Automatyzacja procesu** albo w widoku tygodniowym automatyzacji procesu. Na przykład, jeśli menedżer ds. rozrachunków z dostawcami zdecyduje się wygenerować wszystkie czeki dla dostawców krajowych w środę zamiast w poniedziałek, może znaleźć wystąpienie w widoku tygodniowym i wybrać **Widok/Edycja – Seria**. W przypadku edytowania serii system monituje o określenie, czy zmiana ma być wprowadzana do wszystkich istniejących wystąpień, czy tylko do nowych wystąpień. Wystąpienia historyczne, które mają już stan **Zakończone** lub które zakończyły się ze stanem **Błąd** nie zostaną zmienione.

Można również dodać nowe wystąpienie lub zmienić istniejące wystąpienie. Na przykład następne wystąpienie propozycji płatności zaplanowano na środę 1 stycznia, ale ta data jest świętem. Możesz zmienić wystąpienie z tygodniowego widoku automatyzacji procesu lub ze strony **Automatyzacja procesu**. Zostanie otwarta strona, w której są widoczne szczegóły harmonogramu oraz kryteria propozycji płatności. W tym miejscu można edytować zaplanowaną datę i godzinę. Można również edytować kryteria propozycji płatności, jeśli są wymagane zmiany. Na przykład w przypadku zmiany zaplanowanej daty wystąpienia płatności od 1 stycznia do 2 stycznia może być również konieczna zmiana dat względnych dla daty „do”.

Można również wyłączyć wystąpienie lub serię. Aby wyłączyć i wstrzymać przetwarzanie wystąpienia, wybierz je w widoku tygodniowym automatyzacji procesu, a następnie wybierz opcję **Wyłącz**. Serię można wyłączyć na stronie **Automatyzacja procesu**.

## <a name="security-for-payment-proposal-automations"></a>Bezpieczeństwo automatyzacji propozycji płatności

Następujące obowiązki i uprawnienia zostały dodane dla automatyzacji propozycji płatności dostawcy. Te obowiązki i uprawnienia są domyślnymi ustawieniami zabezpieczeń, ale można je zmieniać w zależności od wymagań organizacji. Na przykład, jeśli nie tylko menedżer ds. rozrachunków z dostawcami, ale także urzędnik płatności rozrachunków z dostawcami mogą edytować i tworzyć harmonogram cykliczny, przypisz obowiązek **Obsługa harmonogramu cyklicznego** do osoby na stanowisku urzędnika płatności rozrachunków z dostawcami.

| Obowiązek                              | Rola                                                                       | Uprawnienia |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Obsługa serii harmonogramu          | Menedżer ds. rozrachunków z dostawcami                                                   | Obowiązek ten przyznaje prawa do tworzenia i obsługiwania serii automatyzacji propozycji płatności oraz wystąpień przez następujące uprawnienia:<ul><li>Obsługa wystąpień harmonogramu</li><li>Obsługa serii harmonogramu</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Wyświetl widok tygodniowy wystąpień</li></ul> |
| Zapytanie o wystąpienia harmonogramu | Pracownik ds. rozrachunków z dostawcami, pracownik scentralizowanych płatności rozrachunków z dostawcami | Obowiązek ten przyznaje prawa wyświetlania wystąpień automatyzacji propozycji płatności oraz wystąpień przez następujące uprawnienia:<ul><li>Wyświetlanie wystąpień harmonogramu</li><li>Wyświetl widok tygodniowy wystąpienia</li></ul> |
| Zapytanie o serię harmonogramu      | None                                                                       | Obowiązek ten przyznaje prawa do przeglądania ustawień serii i zdarzeń poprzez następujące uprawnienia:<ul><li>Wyświetlanie wystąpień harmonogramu</li><li>Wyświetlanie strony listy wystąpień</li><li>Wyświetl widok tygodniowy wystąpienia</li></ul>|
| Obsługa wystąpień harmonogramu     | None                                                                       | Obowiązek ten przyznaje prawa do tworzenia i obsługiwania wystąpienia przez następujące uprawnienia:<ul><li>Obsługa wystąpień harmonogramu</li><li>Wyświetl widok tygodniowy wystąpienia</li></ul> |
