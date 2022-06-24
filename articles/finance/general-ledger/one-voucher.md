---
title: Pojedynczy załącznik
description: Pojedynczy załącznik dla arkuszy finansowych (arkusza finansowego, arkusza środków trwałych, arkusza płatności dla dostawców itd.) umożliwia wprowadzenie wielu transakcji księgi podrzędnej w kontekście jednego załącznika.
author: kweekley
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: kfend
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: fa7a519b87bd5933b8b672f9f9b3e230fd7f2eb4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896413"
---
# <a name="one-voucher"></a>Pojedynczy załącznik

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


## <a name="what-is-one-voucher"></a>Co to jest „pojedynczy załącznik”?

Istniejąca funkcjonalność arkuszy finansowych (arkusza finansowego, arkusza środków trwałych, arkusza płatności dla dostawców itd.) umożliwia wprowadzenie wielu transakcji księgi podrzędnej (z odbiorcami, z dostawcami, na środkach trwałych, w projekcie i bankowych) w kontekście jednego załącznika. Microsoft nazywa tę funkcjonalność *pojedynczym załącznikiem*. Pojedyncze załączniki można tworzyć za pomocą następujących metod:

- Ustaw nazwę arkusza (**Księga główna** \> **Konfiguracja arkusza** \> **Nazwy arkuszy**), tak aby pole **Nowy załącznik** zawierało wartość **Tylko jeden numer załącznika**. Każdy wiersz dodawany do arkusza będzie teraz umieszczany w tym samym załączniku. Dzięki temu załącznik można wprowadzić jako załącznik wielowierszowy, jako konto/konto przeciwstawne w tym samym wierszu lub jako kombinację.

    [![Jeden wiersz.](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > Definicja pojęcia „pojedynczy załącznik” **nie** obejmuje przypadków, gdy nazwy arkuszy skonfigurowano jako **Tylko jeden numer załącznika**, po czym użytkownik wprowadza załącznik zawierający tylko typy kont księgowych. W tym artykule określenie „pojedynczy załącznik” oznacza, że istnieje jeden załącznika zawierający więcej niż jednego dostawcę, odbiorcę, bank, środek trwały lub projekt.

- Umożliwia wprowadzenie załącznika wielowierszowego, gdy nie istnieje żadne konto przeciwstawne.

    [![Załącznik wielowierszowy.](./media/Multi-line.png)](./media/Multi-line.png)

- Umożliwia wprowadzenie załącznika, jeżeli zarówno konto, jak i konto przeciwstawne zawierają typ konta księgi podrzędnej, takie jak **Dostawca**/**Dostawca**, **Odbiorca**/**Odbiorca**, **Dostawca**/**Odbiorca** lub **Bank**/**Bank**.

    [![Załącznik księgi podrzędnej.](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problemy z pojedynczym załącznikiem

Funkcja pojedynczego załącznika powoduje problemy podczas rozliczania, obliczania podatku, wycofywania transakcji, uzgadniania księgi podrzędnej z księgą główną, sprawozdawczości finansowej itd. (Aby uzyskać więcej informacji o problemach, które mogą wystąpić podczas rozliczania, zobacz na przykład [Jeden załącznik z wieloma rekordami odbiorców lub dostawców](../accounts-payable/single-voucher-multiple-customer-vendor-records.md)). Do prawidłowego działania i sprawozdawczości te procesy i raporty wymagają szczegółów transakcji. Mimo iż przy odpowiedniej konfiguracji w organizacji niektóre scenariusze nadal mogą działać prawidłowo, często występują problemy przy wprowadzaniu wielu transakcji do jednego załącznika.

Przypuśćmy na przykład, że księgujesz następujący załącznik wielowierszowy.

[![Przykład załącznika wieloliniowego.](./media/example.png)](./media/example.png)

Następnie generujesz raport **Wydatki według dostawców** w obszarze roboczym **Szczegółowe dane finansowe**. W tym raporcie salda kont wydatków są grupowane według grupy dostawców, a potem według dostawców. Podczas generowania raportu system nie może ustalić, które grupy dostawców/dostawcy ponieśli wydatek w kwocie 250,00. Ponieważ brakuje szczegółów transakcji, system zakłada, że cały wydatek 250,00 został poniesiony przez pierwszego dostawcę znalezionego w załączniku. W związku z tym wydatek 250,00, który został uwzględniony w saldzie konta głównego 600120, jest wyświetlana dla tej grupy dostawców/dostawcy. Jest jednak bardzo prawdopodobne, że pierwszy dostawca w załączniku nie jest właściwym dostawcą. Dlatego raport jest prawdopodobnie błędny.

[![Raport wydatków według dostawców.](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>Przyszłość funkcjonalności pojedynczego załącznika

Ta funkcja jest ostatecznie przestarzała z powodu problemów, które mogą wystąpić podczas korzystania z Pojedynczego załącznika. Jednak ponieważ istnieją luki funkcjonalne, które zależą od tej funkcji, wycofanie nie nastąpi od razu. Wycofanie odbędzie się według następującego harmonogramu:

- **Wydanie z wiosny 2018 r.** — Ta funkcjonalność jest wyłączona za pomocą parametru **Zezwalaj na wiele transakcji w jednym załączniku** na karcie **Ogólne** na stronie **Parametry księgi głównej**. Można ją jednak ponownie włączyć, jeśli w organizacji występuje scenariusz, który należy do jednej z luk funkcjonalnych wymienionych w dalszej części tego artykułu.

    - Jeśli scenariusz biznesowy nie wymaga Pojedynczego załącznika, zaleca się wyłączenie tej funkcji. Jeśli użyjesz go, mimo że istnieje inne rozwiązanie, firma Microsoft nie usunie „błędów” w obszarach zidentyfikowanych w dalszej części tego artykułu.
    - Zalecamy zaprzestanie korzystania z Pojedynczego załącznika na integracje, chyba że potrzebujesz funkcjonalności dla jednej z udokumentowanych luk funkcjonalnych.

- **Późniejsze wydania** – Niektóre z podanych wymagań biznesowych można zaspokoić tylko za pomocą funkcjonalności pojedynczego załącznika. Firma Microsoft musi zagwarantować, że po wycofaniu funkcjonalności wszystkie określone wymagania biznesowe będą spełniane w systemie. Dlatego nowe funkcje będą prawdopodobnie dodawane, aby wypełnić luki funkcjonalne. Firma Microsoft nie może zapewnić konkretnego rozwiązania, ponieważ każda luka w funkcjach jest inna i musi być oceniana na podstawie wymagań biznesowych. Niektóre luki funkcjonalne zostaną prawdopodobnie zastąpione funkcjami, które pomogą spełnić określone wymagania biznesowe. Jednak inne luki można wypełnić, kontynuując zezwalanie na zapis w dzienniku, tak jak w przypadku użycia Pojedynczego załącznika, ale ulepszając system, aby śledził więcej szczegółów w razie potrzeby.

Po wypełnieniu wszystkich luk funkcjonalnych firma Microsoft komunikuje się z firmą, że ta funkcja będzie przestarzała. Jednak deprecja będzie obowiązywać przez przynajmniej rok po tym komunikacie. Firma Microsoft nie może podać oszacowania, kiedy funkcja Jednego załącznika będzie przestarzała, ale prawdopodobnie upłyną co najmniej dwa lata, zanim nastąpi wycofanie. Zasadą firmy Microsoft jest pozostawienie co najmniej 12 miesięcy między ogłoszeniem wycofanej funkcjonalności a faktycznym wycofaniem, tak aby klienci i niezależni dostawcy oprogramowania (ISV) mieli czas na reakcję na zmianę. Na przykład organizacja może być zmuszona do zaktualizowania swoich procesów biznesowych, jednostek i integracji.

Wycofanie Pojedynczego załącznika to znacząca zmiana, o której będziemy szeroko informować. W ramach tej komunikacji Microsoft zaktualizuje ten artykuł, opublikuje wpis na blogu Microsoft Dynamics 365 Finance, zaktualizuje artykuł „Usunięte lub przestarzałe funkcje”, poinformuje o zmianie na odpowiednich konferencjach Microsoft i tak dalej.

## <a name="why-use-one-voucher"></a>Dlaczego watro używać funkcjonalności pojedynczego załącznika?

Na podstawie rozmów z klientami sporządziliśmy listę scenariuszy, w których klienci korzystają z funkcji pojedynczego załącznika, oraz przyczyn, dla których jej używają. Niektóre z podanych wymagań biznesowych można zaspokoić tylko za pomocą funkcjonalności pojedynczego załącznika. Jednak w wielu scenariuszach alternatywne rozwiązania spełniają te same wymagania biznesowe.

### <a name="scenarios-that-require-one-voucher"></a>Scenariusze wymagające funkcjonalności pojedynczego załącznika

Poniższe scenariusze można realizować tylko przy użyciu funkcjonalności pojedynczego załącznika. Jeśli organizacja stosuje którykolwiek z tych scenariuszy, należy włączyć możliwość wprowadzania wielu transakcji w jednym załączniku, zmieniając wartość ustawienia **Zezwalaj na wiele transakcji w jednym załączniku** na stronie **Parametry księgi głównej**. Opisane luki funkcjonalne zostaną uzupełnione za pomocą innych funkcji zawartych w późniejszych wydaniach.

> [!NOTE]
> [Dla każdego z poniższych scenariuszy pole **Zezwalaj na wiele transakcji w ramach jednego załącznika** musi mieć ustawioną wartość tak w skróconej karcie **Ogólne** na stronie **Parametry księgi głównej**.]

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Księgowanie płatności dla dostawców lub od odbiorców w postaci zbiorczej na koncie bankowym

**Scenariusz** Organizacja przekazuje bankowi listę dostawców i należnych im kwot, a bank na podstawie tej listy płaci dostawcom w imieniu organizacji. Bank księguje sumę płatności jako pojedynczą wypłatę z rachunku bankowego.

Sumowanie płatności dla dostawców jest możliwe tylko za pośrednictwem funkcji pojedynczego załącznika. Każdy dostawca jest wprowadzany jako osobny wiersz, co ma zachować szczegóły w księdze podrzędnej modułu Rozrachunki z dostawcami. Jednak zsumowana kwota wszystkich płatności jest umieszczana w jednym wierszu konta bankowego. W związku z tym wypłata jest wyświetlana jako jedna sumaryczna kwota w księdze podrzędnej banku.

**Scenariusz** Organizacja wpłaca płatności od odbiorców, lub bank wpłaca płatności od odbiorców w imieniu organizacji, a cała wpłacona kwota jest wyświetlana jako jedna wpłata na rachunku bankowym.

Sumowanie płatności od odbiorców jest zazwyczaj realizowane za pomocą funkcjonalności wpłat. Jednak jeśli w metodzie płatności stosujesz „łączenie”, ten scenariusz będzie obsługiwany tylko za pomocą funkcjonalności pojedynczego załącznika. Płatności od odbiorców są wprowadzane w taki sam sposób, jak opisano dla sumowania płatności do dostawców.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Mechanizm grupowanie transakcji ze zdarzenia biznesowego

**Scenariusz** Organizacja ma jedno zdarzenie biznesowe, które inicjuje wiele transakcji. Jednak dział księgowości chce wyświetlać wpisy księgowe razem, co ułatwi kontrolę.

Jeśli organizacja musi wyświetlać zapisy księgowe ze zdarzenia biznesowego razem, musi używać funkcjonalności pojedynczego załącznika. 

### <a name="country-specific-features"></a>Funkcje specyficzne dla kraju

**Scenariusz** Funkcja jednolitego dokumentu administracyjnego (SAD) w Polsce obecnie wymaga używania jednego załącznika. Dopóki dla tej funkcji nie będzie dostępna opcja grupowania, należy nadal korzystać z funkcjonalności pojedynczego załącznika. Mogą istnieć dodatkowe funkcje specyficzne dla krajów, które wymagają funkcjonalności pojedynczego załącznika.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Arkusz zaliczek od odbiorców zawierający podatki w wielu „wierszach”

W tym scenariuszu odbiorcy w pojedynczym załączniku są tym samym odbiorcą, ponieważ transakcja symuluje wiersze zamówienia odbiorcy. Zaliczka musi zostać wprowadzona w jednym załączniku, ponieważ obliczanie podatku musi nastąpić w stosunku do „wierszy” jednej płatności dokonanej przez odbiorcę.

### <a name="customer-reimbursement"></a>Zwrot nadpłaty do odbiorcy

**Scenariusz A** Odbiorca dokonuje przedpłaty za zamówienie, a wiersze zamówienia mają różne podatki, które należy zarejestrować dla przedpłaty. Płatność w postaci zaliczki od odbiorcy to transakcja, które symuluje wiersze zamówienia, tak aby odpowiedni podatek mógł zostać zarejestrowany dla kwoty w każdym wierszu.

Jeśli zadanie okresowe Zwrot nadpłaty zostanie uruchomione z poziomu modułu Rozrachunki z odbiorcami, utworzy transakcję przeniesienia salda od odbiorcy do dostawcy. W tym scenariuszu trzeba użyć funkcji pojedynczego załącznika, aby zwrócić pieniądze odbiorcy.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Obsługa środków trwałych: amortyzacja wyrównująca, rozbicie środka trwałego, obliczania amortyzacji przy likwidacji
W wersjach 10.0.21 i nowszych transakcje środków trwałych służące do amortyzacji wyrównującej, podziału środka trwałego i obliczania amortyzacji z tytułu likwidacji środka trwałego będą tworzone przy użyciu różnych numerów załączników.

### <a name="bills-of-exchange-and-promissory-notes"></a> Weksle i skrypty dłużne
Weksle i skrypty dłużne wymagają używania pojedynczego załącznika, ponieważ transakcja powoduje przeniesienie salda odbiorcy lub dostawcy z jednego konta księgowego w module Rozrachunki z odbiorcami/Rozrachunki z dostawcami do innego konta na podstawie stanu płatności.

## <a name="scenarios-that-dont-require-one-voucher"></a>Scenariusze niewymagające funkcjonalności pojedynczego załącznika

Poniższe scenariusze można realizować innymi sposobami, bez używania funkcji pojedynczego załącznika.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Księgowanie płatności od odbiorców na koncie bankowym

Organizacja wpłaca płatności od odbiorców, lub bank wpłaca płatności od odbiorców w imieniu organizacji, a cała wpłacona kwota jest wyświetlana jako jedna wpłata na rachunku bankowym.

Sumowanie płatności od odbiorców jest realizowane za pomocą funkcjonalności wpłat, jeśli w metodzie płatności nie jest stosowane „łączenie”.

### <a name="netting"></a>Kompensacja

W netowaniu salda dla odbiorcy i dostawcy są kompensowane względem siebie, ponieważ dostawca i odbiorca to ta sama strona. To podejście minimalizuje wymianę pieniędzy między organizacją a stroną będącą odbiorcą/dostawcą.

Netowanie można realizować poprzez wprowadzenie zwiększenia i zmniejszenia w oddzielnych załącznikach, a następnie zaksięgowanie kompensacji na rozliczeniowym koncie księgowym.

### <a name="post-in-summary-to-the-general-ledger"></a>Księgowanie sumaryczne w księdze głównej

Organizacje często chcą księgować w księdze głównej sumarycznie, aby zminimalizować ilość danych. Jednak zazwyczaj takie organizacje wciąż wymagają zachowania szczegółów transakcji. Jeśli księgowanie odbywa się sumarycznie za pomocą jednego załącznika, szczegóły transakcji są nieznane i nie można ich zachować.

- Ponieważ obecnie szczegóły transakcji nie mogą być przechowywane, zalecamy, aby **nie** używać funkcjonalności pojedynczego załącznika do księgowania sumarycznego.
- Po usunięciu obsługi funkcji pojedynczego załącznika można w arkuszach wdrożyć struktury Dokument źródłowy i Księgowanie. Struktury te będą przechowywały szczegóły transakcji i umożliwią sumowanie do księgi głównej.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Rozliczanie wielu niezaksięgowanych płatności względem jednej faktury

Ten scenariusz zwykle występuje w organizacjach, gdzie odbiorcy stosują wiele metod płatności za zakupy. W tym scenariuszu organizacja musi mieć możliwość rejestrowania wielu niezaksięgowanych płatności i rozliczania ich względem faktury dla odbiorcy.

Nowa funkcja, którą dodano w programie Microsoft Dynamics 365 for Operations w wersji 1611 (z listopada 2016), umożliwia rozliczanie wielu niezaksięgowanych płatności względem jednej faktury. Nie trzeba już wprowadzać wielu płatności od odbiorców w jednym załączniku.

### <a name="import-bank-statement-transactions"></a>Importowanie transakcji z wyciągów bankowych

Banki często wysyłają i otrzymują płatności w imieniu organizacji, a transakcje te są rejestrowane w usłudze Finance za pomocą pliku otrzymanego z banku. Organizacje często chcą grupować te transakcje przy użyciu numeru wyciągu bankowego znajdującego się w pliku. Ponieważ każda transakcja jest wyświetlana szczegółowo na wyciągu bankowym, nie trzeba dokonywać podsumowywania w księdze podrzędnej banku.

Transakcje można grupować przy użyciu innych pól w arkuszu, takich jak numer partii w arkuszu lub numer dokumentu.


### <a name="transfer-balances"></a>Przeniesienie sald

Organizacja może potrzebować przenieść saldo od jednego dostawcy do innego dostawcy, na przykład z powodu błędu lub przejęcia odpowiedzialności przez drugiego dostawcę. Tego typu przeniesienia odbywają się również dla typów kont takich jak **Odbiorca** i **Bank**.

Przeniesienia sald z jednego konta (dostawcy, odbiorcy, bankowego itd.) na inne konto mogą się odbywać za pomocą osobnych załączników, a kompensacja może być księgowana na rozliczeniowym koncie księgowym.

### <a name="enter-beginning-balances"></a>Wprowadzanie sald początkowych

Organizacje często wprowadzają salda początkowe na kontach księgi podrzędnej (dostawców, odbiorców, środków trwałych itd.) jako jedną transakcję załącznika. Salda początkowe dla każdego konta księgi podrzędnej można wprowadzić jako osobne załączniki, a kompensację można zaksięgować na rozliczeniowym koncie księgowym.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Poprawianie wpisu księgowego zaksięgowanego dokumentu odbiorcy lub dostawcy

Organizacja może potrzebować poprawić zapis księgowy zaksięgowanej faktury na koncie księgowym w module Rozrachunki z odbiorcami lub Rozrachunki z dostawcami, ale odnośnej faktury nie można cofnąć ani poprawić za pomocą żadnego innego mechanizmu.

Jeżeli trzeba dokonać korekty na koncie księgowym modułu Rozrachunki z odbiorcami lub z Rozrachunki z dostawcami, należy to zrobić bezpośrednio na koncie księgowym. Nie można dokonać korekty poprzez zaksięgowania za pośrednictwem dostawcy lub odbiorcy. Takie podejście wymaga, aby korekta została przeprowadzona podczas „przestoju”, w którym konto księgowe pozwala tymczasowo na wprowadzanie ręczne.

### <a name="the-system-allows-it"></a>System na to pozwala

Organizacje często korzystają z funkcjonalności pojedynczego załącznika dlatego, że po prostu system na to pozwala. Niestety, nie wiedzą o skutkach używania tego mechanizmu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
