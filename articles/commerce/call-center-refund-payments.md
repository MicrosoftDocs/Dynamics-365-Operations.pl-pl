---
title: Przetwarzanie płatności zwrotów w biurach obsługi
description: W tym artykule wyjaśniono, w jaki sposób zwroty płatności są generowane przez centra obsługi telefonicznej, gdy tworzone są zwroty lub gdy zamówienia lub wiersze zamówienia są anulowane.
author: hhainesms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 330674a31dc59e99ffedb82d0896c64214562eb3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880121"
---
# <a name="refund-payment-processing-in-call-centers"></a>Przetwarzanie płatności zwrotów w biurach obsługi

W tym artykule wyjaśniono, w jaki sposób zwroty płatności są generowane przez centra obsługi telefonicznej, gdy tworzone są zwroty lub gdy zamówienia lub wiersze zamówienia są anulowane.

Użytkownik, który tworzy zamówienie zwrotu dla klienta jako użytkownika centrum obsługi w centrali Microsoft Dynamics 365 Commerce, używa strony **Zamówienie zwrotu** do utworzenia wstępnej autoryzacji materiałów zwrotu (RMA). Autoryzacja zwrotu definiuje produkty, które odbiorca chce zwrócić lub zmienić, i tworzy połączone zamówienie zwrotu sprzedaży o typie zamówienia **Zwrot zamówienia**. To połączone zwrócone zamówienie służy do śledzenia księgowania zwróconych zapasów oraz wszelkich zaksięgowanych faktur korygujących lub zwrotów płatności.

Jeśli opcja **Włącz zakończenie zamówienia** dla kanału obsługi ma wartość **Tak**, użytkownik wywołania, który tworzy autoryzację zwrotu, musi uruchomić przepływ przetwarzania zakończenia zamówienia, wybierając przycisk **Wykonaj** na stronie **Zwrot zamówienia**. Funkcja **Wykonaj** zawiera obliczane podsumowanie zwrotu, które przedstawia kwotę zwrotu, która jest należna. Dodatkowo, gdy jest poprawnie skonfigurowany, systematycznie tworzy wiersz płatności zwrotu dla zwróconego zamówienia.

Logika call center określa metodę płatności dla linii płatności zwrotu na podstawie metody płatności użytej w pierwotnym zamówieniu. Jeśli utworzone zamówienie zwrotu nie jest połączone z oryginalnym zamówieniem, stosowana jest domyślna metoda płatności pobierana z parametru systemowego.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>Sposób określania metody płatności stosowanej dla zamówienia zwrotu przez centrum obsługi

Centrum obsługi telefonicznej korzysta z metody płatności pierwotnego zamówienia, aby określić metodę płatności, jaką należy zastosować do zamówienia zwrotu. Poniżej przedstawiono sposób działania tego procesu w przypadku następujących oryginalnych metod płatności:

- **Zwykłe** (gotówka) lub **Czek** — jeśli tworzone zamówienie zwrotu odwołuje się do oryginalnego zamówienia, za które zapłacono przy użyciu zwykłego (gotówki) lub typu płatności czeku, konfiguracje odwołań aplikacji do funkcji obsługi na stronie **Metody zwrotu dla centrum obsługi**. Ta strona umożliwia organizacjom zdefiniowanie według waluty zamówienia, w jaki sposób zwroty są wydawane klientom za zamówienia, za które pierwotnie zapłacono przy użyciu zwykłego typu płatności lub czeku. Strona **Metody zwrotu biura obsługi** umożliwia również organizacjom określenie, czy czek zwrotu wygenerowany przez system ma zostać wysłany do odbiorcy. W tych scenariuszach logika centrum obsługi odwołuje się do waluty zamówienia zwrotu, a następnie używa wartości **Metody płatności detalicznej dla tej waluty**, aby utworzyć wiersz płatności zwrotu w zamówieniu zwrotu. Później arkusz płatności odbiorców rozrachunków z odbiorcami (AR), który używa zmapowanej metody płatności AR, jest połączony z walutą.

    Na poniższej ilustracji przedstawiono konfigurację scenariusza, w którym klient zwraca produkty z zamówienia sprzedaży, które jest połączone z walutą USD i które zostało pierwotnie opłacone przy użyciu zwykłego typu płatności lub czeku. W tym scenariuszu zwrot środków zostanie przekazany klientowi za pośrednictwem wygenerowanego przez system czeku zwrotnego. Metoda płatności **REF-CHK** AR została skonfigurowana jako typ płatności dla czeku zwrotu.

    ![Konfiguracja metod zwrotu dla centrum obsługi dla oryginalnych płatności zwykłych i za pomocą czeku.](media/callcenterrefundmethods.png)

    > [!NOTE]
    > Konto odbiorcy nie jest obsługiwaną metodą zwrotu w przypadku płatności gotówką lub czekiem.

- **Karta kredytowa** – Gdy tworzone zamówienie zwrotu odwołuje się do oryginalnego zamówienia, za które zapłacono kartą kredytową, logika centrum obsługi dla płatności zwrotów jest taka sama, jak oryginalna karta kredytowa do zamówienia zwrotu.
- **Karta lojalnościowa** – Gdy utworzone zamówienie zwrotu odwołuje się do oryginalnego zamówienia, za które zapłacono przy użyciu karty lojalnościowej klienta, logika centrum obsługi telefonicznej dla płatności refundacji stosuje zwrot do tej samej karty lojalnościowej.
- **Karta upominkowa** (wewnętrzna) – Gdy utworzone zamówienie zwrotu odwołuje się do oryginalnego zamówienia, za które zapłacono przy użyciu karty podarunkowej, która została wydana z Dynamics 365 Commerce (wewnętrzna funkcjonalność karty podarunkowej), logika call center dotycząca płatności zwrotnych stosuje zwrot na ten sam oryginalny numer karty podarunkowej .
- **Karta upominkowa (Zewnętrzna)** — Jeśli zamówienie zwrotu, które jest tworzone, odwołuje się do oryginalnego zamówienia, za które zapłacono za pomocą zewnętrznej karty upominkowej innej firmy, logika wywołania dla płatności zwrotów jest stosowana domyślna metoda płatności zwrotu zdefiniowana na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry centrum obsługi**.

Jeśli oryginalny typ płatności dla zamówienia jest nieznany z dowolnej przyczyny lub gdy do zapłaty za oryginalne zamówienie zostało używanych wiele metod płatności, logika wywołania stosuje domyślną metodę zwrotu płatności zdefiniowaną na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry centrum obsługi**.

Na poniższej ilustracji pokazano pole **Metoda płatności** na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry biura obsługi**.

![Pole Metoda płatności na karcie Autoryzacja zwrotu/Zwrot na stronie Parametry biura obsługi.](media/callcenterrefundparameters.png)

> [!NOTE]
> Opisane wcześniej reguły przetwarzania zwrotów dotyczą także zamówień lub wierszy zamówień, które użytkownik centrum obsługi anuluje w programie Commerce Headquarters. Jeśli anulowanie zamówienia lub określonych wierszy zamówienia powoduje nadpłatę, do generowania wierszy płatności zwrotu będą używane te same reguły.

Zwykle zamówienie zwrotu przechodzi przez standardowy proces, w którym zapasy są odbierane (lub odrzucane), dokument dostawy jest księgowany przy zamówieniu zwrotu, a następnie jest uruchamiany proces księgowania faktury dla zamówienia zwrotu. Zamówienie zwrotu sprzedaży jest połączone i generowane systemowo w ramach procesu tworzenia zamówienia zwrotu. W typowych scenariuszach zwroty płatności nie są wydawane klientom, dopóki nie zostanie zaksięgowana faktura za zwrot zamówienia.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>Co się dzieje w przypadku zaksięgowania faktury w zamówieniu zwrotu sprzedaży

Poniższe scenariusze wyjaśniają, co się dzieje, gdy faktura jest księgowana w zwrotnym zamówieniu sprzedaży:

- Jeśli zwrot kosztów zamówienia zwrotu dotyczy karty kredytowej, po zaksięgowaniu faktury zostaje wywołana dodatkowa logika. Ta logika wywołuje metodę zwrotu płatności na kartę kredytową odbiorcy. Załącznik zwrotu płatności odbiorcy jest także tworzony i systemowo księgowany na koncie odbiorcy. Ten arkusz płatności zostanie rozliczony z kuponem faktury korygującej zamówienia zwrotu.
- Jeśli płatność zwrotna, która musi zostać wystawiona, dotyczy typu płatności czekiem, tworzony jest kupon płatności odbiorcy korzystający z metody płatności AR i należy go ręcznie zaksięgować lub wydrukować, zanim będzie można zaksięgować dowód płatności na koncie odbiorcy. Aby przetworzyć zwrot, użytkownicy mogą użyć strony **Arkusz płatności odbiorcy** w rozrachunkach z odbiorcami lub wyspecjalizowanej strony **Przetwarzanie dokumentu zwrotu** w sieci sprzedaży i handlu.
- Jeśli płatność zwrotu, która musi zostać wydana, jest typu wewnętrznej karty upominkowej lub karty lojalnościowej, podczas fakturowania zamówienia zwrotu załącznik płatności zwrotu jest tworzony i księgowany na koncie odbiorcy. Ten etap fakturowania dodaje również kwotę zwrotu z powrotem do wewnętrznie śledzonego salda karty podarunkowej klienta lub salda punktów lojalnościowych.
- Jeśli metoda płatności korzystająca z funkcji **Odbiorcy** (na przykład konto odbiorcy) jest połączona z zamówieniem zwrotu sprzedaży, sprawdzanie poprawności limitu kredytu jest ignorowane podczas przetwarzania płatności. W tym kontekście nie jest tworzony ani księgowany załącznik płatności. Gdy typ płatności odbiorcy jest używany w zamówieniu zwrotu, kupon faktury korygującej tworzony w procesie księgowania faktury służy jako bon kredytowy klienta i wskazuje zwrot środków na saldo AR klienta.

## <a name="advance-credit"></a>Kredyt zaliczkowy

Gdy użytkownik przetwarza zamówienia zwrotu jako użytkownika centrum obsługi, w którym opcja **Włącz zakończenie zamówienia** ma wartość **Tak**, może wystąpić wyjątek w poprzednio opisanym procesie księgowania płatności zwrotu, jeśli użytkownik wywołania, który tworzy zamówienie zwrotu, ustawi dla opcji **Kredyt zaliczkowy** opcję **Tak** na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry centrum obsługi**. W takim przypadku zwrot płatności następuje niezwłocznie po pomyślnym przesłaniu zamówienia zwrotu za pomocą funkcji **Prześlij** na stronie **Podsumowania zwrotu**. System natychmiast tworzy załącznik przedpłaty płatności odbiorcy dla wartości zwrotu, nawet jeśli samo zamówienie sprzedaży zwrotu nie zostało jeszcze zafakturowane. Takie podejście można zastosować w sytuacjach, gdy organizacja musi z wyprzedzeniem wydawać zwroty kosztów klientom z powodu problemów z obsługą klienta i nie chce wymagać, aby zwrócone zapasy zostały odebrane przed wydaniem zwrotu.

## <a name="replacement-orders"></a>Zamówienia wymiany

Gdy zostanie wystawione zamówienie zwrotu, funkcja **Zamówienie wymiany** może zostać użyta do wygenerowania nowego zamówienia sprzedaży dla odbiorcy. Tej metody można używać w scenariuszach wymiany. Funkcja **Zamówienia wymiany** tworzy inne zamówienie sprzedaży dla nowych towarów, które muszą zostać wysłane, ale łącze odsyłacze na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry biura obsługi** powoduje połączenie zamówienia wymiany, autoryzacji zwrotu i zwróconego zamówienia sprzedaży.

Podczas przetwarzania płatności z tytułu zamówienia wymiany organizacje mają dwie opcje:

- Zwróć odbiorcy za zamówienie zwrotu na podstawie oryginalnej metody płatności, a następnie zbierz osobną płatność dla zamówienia wymiany. Do użycia tej opcji nie jest wymagana żadna dodatkowa konfiguracja.
- Ustaw opcję **Zastosuj kredyt** na **Tak** na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry biura obsługi**. W tym przypadku metoda płatności odbiorcy jest systematycznie stosowana zarówno do zamówienia zwrotu, jak i do zamówienia wymiany. Ta opcja zapobiegnie wystawionej zewnętrznej płatności zwrotu. Pomaga także zapobiec przetwarzaniu płatności w transakcji. Może to być przydatne w sytuacjach, gdy przetwarzana jest równa wymiana, a organizacja woli użyć kuponu kredytowego, który jest generowany podczas fakturowania zamówienia zwrotu, aby zapłacić za fakturę wygenerowaną przez zamówienie wymiany. Jeśli w opcji **Zastosuj kredyt** jest ustawiona wartość **Tak**, po wygenerowaniu obu tych dokumentów finansowych organizacja musi ręcznie rozliczyć fakturę korekty z fakturą zamówienia wymiany.

Ustawienie **Tak** dla opcji **Zastosuj kredyt** ma zastosowanie tylko w przypadku, gdy zamówienie zwrotu zostanie połączone z zamówieniem wymiany. W tym przypadku metoda płatności odbiorcy, która będzie używana do systemowego płacenia za zwrot, a zamówienie wymiany jest zdefiniowane za pomocą pola **Zastosuj metodę płatności kredytów** na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry centrum obsługi**. W tym polu można wybrać tylko płatność typu płatności funkcji **Odbiorcy**.

> [!NOTE]
> W przypadku zamówienia zwrotu, które nie ma połączonego zamówienia wymiany, ustawienie **Tak** dla opcji **Zastosuj kredyt** nie będzie mieć wpływu na logikę płatności zamówienia zwrotu, ponieważ to ustawienie dotyczy tylko zamówień wymiany.

![Pole zastosuj płatność kredytową na karcie Autoryzacja zwrotu/Zwrot na stronie Parametry biura obsługi.](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Jeśli użytkownicy tworzący zamówienia wymiany planują korzystanie z opcji **Zastosuj kredyt**, nie powinni uruchamiać funkcji **Zakończenie** dla zamówienia zwrotu przed ustawieniem opcji **Zastosuj kredyt** na wartość **Tak**. Po uruchomieniu funkcji **Zakończenie** płatność zwrotu jest obliczana i stosowana do zamówienia sprzedaży dla zwrotu. Próba ustawienia opcji **Zastosuj kredyt** na wartość **Tak**, jeśli płatność zwrotu już została obliczona i zastosowana nie wywoła ponownego obliczenia płatności zwrotu, a metoda płatności wybrana w polu **Zastosuj metodę płatności kredytowej** nie będzie stosowana. Jeśli w tym kontekście ma być używana opcja **Zastosuj kredyt**, użytkownik musi usunąć zamówienie wymiany i autoryzację zwrotu, a następnie uruchomić od nowa i utworzyć nową autoryzację zwrotu. W tej chwili użytkownik musi upewnić się, że opcja **Zastosuj kredyt** ma wartość **Tak** przed uruchomieniem funkcji **Zakończenie**.

## <a name="payment-overrides-for-call-center-returns"></a>Zastąpienia płatności dla zwrotów z centrum obsługi

Chociaż logika call center systematycznie określa metodę zwrotu pieniędzy w sposób opisany wcześniej w tym artykule, użytkownicy mogą czasami chcieć zastąpić te płatności. Na przykład użytkownik może edytować lub usunąć istniejące wiersze płatności zwrotu i zastosować nowe linie płatności. Zwroty obliczane przez system mogą być zmieniane tylko przez użytkowników, którzy mają odpowiednie uprawnienia zastępowania. Te uprawnienia można skonfigurować na stronie **Zastępowanie uprawnień** w sieci sprzedaży i handlu. Aby można było zastąpić płatność zwrotem, użytkownik musi być połączony z rolą zabezpieczeń, w której ustawiono opcję **Zezwalaj na alternatywną płatność** na **Tak** na stronie **Uprawnienia do zastępowania**.

![Zezwalaj na alternatywną opcję płatności na stronie Zastępowanie uprawnień.](media/overridepermissions.png)

Ewentualnie organizacja może ustawić opcję **Zezwalaj na zastępowanie płatności** na wartość **Tak** na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry centrum obsługi**. W takim przypadku należy wybrać kod zastąpienia zabezpieczeń w polu **Kod zastąpienia zabezpieczeń**. Kod zastępujący zabezpieczenia to kod alfanumeryczny, który musi być zarządzany zewnętrznie, ponieważ użytkownicy nie mogą go wyświetlać w Commerce headquarters po jego ustawieniu. Kod zastąpienia zabezpieczeń powinien być znany tylko przez kilka zaufanych osób w organizacji. Gdy opcja **Zezwalaj na zastępowanie płatności** ma wartość **Tak**, użytkownicy, którzy nie mają odpowiednich uprawnień roli, próbują zmienić metodę płatności w zamówieniu zwrotu, będą mieć możliwość wprowadzenia kodu zastąpienia zabezpieczeń. Jeśli go nie znasz lub menedżer lub kierownik nie może go wprowadzić na stronie, nie będzie mógł zastąpić metody płatności zwrotu.

> [!NOTE]
> Jeśli kod zastąpienia zabezpieczeń zostanie utracony lub zapomniany, organizacja będzie musiał go zresetować, definiując nowy kod zastąpienia zabezpieczeń w polu **Kod zastąpienia zabezpieczeń** na karcie **Autoryzacja zwrotu/Zwrot** na stronie **Parametry centrum obsługi**.

![Parametry nadpisania płatności na karcie Autoryzacja zwrotu/Zwrot na stronie Parametry biura obsługi.](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Zanim organizacje spróbują zastąpić zwroty płatności korzystające z rodzajów płatności kartą kredytową, powinny sprawdzić, czy ich procesor kart kredytowych umożliwia zwroty niepowiązane. Wielu procesorów wymaga, aby zwroty był księgowane z powrotem na oryginalnej karcie. Każda próba zwrotu pieniędzy na kartę, która nie została wcześniej zarejestrowana, może spowodować błędy księgowania w procesorze.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Metody płatności w biurach obsługi](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]