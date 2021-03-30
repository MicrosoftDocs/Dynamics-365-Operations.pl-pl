---
title: Zarządzanie cenami w sprzedaży detalicznej
description: W tym temacie opisano pojęcia związane z tworzeniem i zarządzaniem cenami sprzedaży w Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3411be3be44b5ca72bcd6b52b335662b1fc16aa4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231183"
---
# <a name="retail-sales-price-management"></a>Zarządzanie cenami sprzedaży w aplikacji Retail

[!include [banner](includes/banner.md)]

Ten temat zawiera informacje o procesie tworzenia i zarządzania ceny sprzedaży w Dynamics 365 Commerce. Koncentruje się na pojęciach występujących w tym procesie oraz na wpływie różnych opcji konfiguracji na ceny sprzedaży.

## <a name="terminology"></a>Terminologia

W tym temacie są wykorzystywane następujące pojęcia:

| Okres | Definicja, zastosowanie i uwagi |
|---|---|
| Cena | Kwota za pojedynczą jednostkę, w jakiej produkt jest sprzedawany w aplikacji klienckiej punktu sprzedaży (POS) lub według zamówienia sprzedaży. W tym temacie termin *cena* zawsze dotyczy ceny sprzedaży, a nie ceny zapasów lub kosztu własnego. |
| Podstawa ceny | Cena ustawiona w polu **Cena** dla zwolnionego produktu. |
| Cena w umowie handlowej | Cena ustawiona w produkcie lub wariancie za pomocą umowy handlowe dla typu **Cen (sprzedaż)**. |
| Najlepsza cena | Jeżeli do produktu można zastosować więcej niż jedną cenę lub rabat, jest to najmniejsza kwota ceny i/lub największa kwota rabatu pozwalająca uzyskać najniższą możliwą kwotę netto, którą musi zapłacić klient. W tym temacie pojęcie najlepszej zawsze określa się jako „najlepszą cenę”. Ta najlepsza cena różni się od i nie powinna być mylona z wartością elementu stałotekstowego **Najlepsza cena** używaną w trybie współbieżności rabatu. |

## <a name="price-groups"></a>Grupy cenowe

Grupy cenowe są sercem mechanizmu zarządzania cenami i rabatami w aplikacji Commerce. Grupy cenowe są używane do przypisywania cen i rabatów do jednostek handlu (tzn. kanałów, katalogów, przynależności i programów lojalnościowych). Grupy cenowe są wykorzystywane dla wszystkich cen i rabatów, dlatego bardzo ważne jest zaplanowanie, jak będą używane, zanim zaczniesz to robić.

Grupa cenowa jako obiekt składa z nazwy, opisu i (opcjonalnie) priorytetu cen. Najważniejszą rzeczą, jaką należy pamiętać o grupach cenowych, jest to, że służą do zarządzania relacjami wiele-do-wielu między rabatami i cenami a jednostkami handlu.

Na ilustracji poniżej przedstawiono sposób używania grup cenowych. Na ilustracji zwróć uwagę, że „Grupa cenowa” jest dosłownie w centrum zarządzania cenami i rabatami. Jednostki handlu, których można używać do zarządzania zróżnicowanymi cenami i rabatami, znajdują się po lewej stronie, a rekordy faktycznych cen i rabatów znajdują się po prawej stronie.

![Grupy cenowe](./media/PriceGroups.png "Grupy cenowe")

Podczas tworzenia grup cenowych nie należy używać jednej grupy cenowej dla różnych typów jednostek handlu. W przeciwnym razie może być trudno określić, dlaczego konkretna cena lub rabat są stosowane do transakcji.

Jak pokazuje czerwona kreskowana linia na ilustracji, aplikacja Commerce obsługuje podstawową funkcjonalność systemu Microsoft Dynamics 365 — grupy cenowe, które są ustawiane bezpośrednio dla odbiorców. Jednak w tym przypadku można korzystać tylko z umów handlowych na cenę sprzedaży. Jeśli chcesz stosować ceny specyficzne dla odbiorców, zalecamy, aby nie ustawiać grup cenowych bezpośrednio dla odbiorców. Zamiast tego należy używać przynależności. 

Należy zauważyć, że jeśli grupa cenowa jest ustawiona na klienta, wówczas ta grupa cenowa zostaje powiązana z nagłówkiem zamówienia sprzedaży zamówień utworzonych dla tego klienta. Jeśli użytkownik zmieni grupę cen w nagłówku zamówienia, wówczas stara grupa cen zostanie zastąpiona nową grupą cen tylko dla bieżącego zamówienia. Na przykład stara grupa cenowa nie będzie miała wpływu na bieżące zamówienie, ale będzie nadal skojarzona z odbiorcą w przyszłych zamówieniach.

W dalszych rozdziałach zawarto więcej informacji na temat jednostek handlu, których można używać do ustawiania odrębnych cen podczas korzystania z grup cenowych. Konfigurowanie cen i rabatów dla wszystkich tych jednostek jest procesem dwuetapowym. Etapy te można wykonać w dowolnej kolejności. Jednak zgodnie z porządkiem logicznym najpierw należy ustawić grupy cenowe dla jednostek, ponieważ ten krok będzie najprawdopodobniej tylko jednorazową konfiguracją wykonywaną podczas wdrażania. Następnie, wraz z tworzeniem cen i rabatów, można ustawiać grupy cenowe indywidualnie dla tych cen i rabatów.

### <a name="channels"></a>Kanały

W branży handlowej bardzo popularne jest stosowanie różnych cen w różnych kanałach. Dwa podstawowe czynniki wpływające na wysokość cen w poszczególnych kanałach to koszty i lokalne warunki rynkowe.

- **Koszty** — im dalej jest kanał od źródła produktu, tym więcej kosztuje utworzenie zapasów produktu. Na przykład świeże artykuły rolne mają ograniczony okres przydatności i szczególne wymagania dotyczące produkcji (na przykład okres wegetacji). W czasie zimy świeża sałata prawdopodobne będzie kosztowała więcej w krajach północnych niż południowych. W przypadku ustawiania cen dla kanałów na dużym obszarze geograficznym prawdopodobnie zechcesz ustawić różne ceny w różnych kanałach.
- **Lokalne warunki rynkowe** — sklep, który ma bezpośredniego konkurenta po drugiej stronie ulicy, będzie znacznie bardziej wrażliwy na ceny niż sklep, który nie ma konkurencji w sąsiedztwie.

### <a name="affiliations"></a>Przynależności

Ogólna definicja przynależności to połączenie lub skojarzenie z grupą. W aplikacji Commerce przynależności są grupami odbiorców. Przynależności są znacznie bardziej elastycznym narzędziem do ustawiania cen i rabatów dla odbiorców niż podstawowa funkcjonalność grup odbiorców i grup rabatowych w systemie Microsoft Dynamics 365. Po pierwsze, przynależności można stosować zarówno do cen, jak i do rabatów, podczas gdy ceny niezwiązane z handlem detalicznym mają inną grupę dla każdego typu rabatu i ceny. Po drugie, odbiorca może należeć do wielu przynależności, ale tylko do jednej grupy cen każdego typu niezwiązanych z handlem detalicznym. I wreszcie przynależności można skonfigurować tak, aby były połączone z odbiorcami, ale nie jest to konieczne. Do anonimowych odbiorców w punkcie sprzedaży można stosować przynależności ad hoc. Typowym przykładem rabatu wykorzystującego przynależność anonimową jest rabat dla starszej osoby lub studenta, gdzie w celu otrzymania rabatu klient musi tylko pokazać kartę członkowską grupy.

Chociaż przynależności są najczęściej powiązane z rabatami, można ich także używać do ustawiania zróżnicowanych cen. Na przykład gdy sprzedawca detaliczny (sieć handlowa) sprzedaje pracownikowi, może chcieć zmienić cenę sprzedaży zamiast stosować rabat od ceny katalogowej. Inny przykład: sprzedawca detaliczny sprzedający zarówno klientom indywidualnym, jak i instytucjonalnym może oferować lepsze ceny klientom instytucjonalnym, ponieważ oni kupują więcej. Funkcja przynależności obsługuje oba te scenariusze.

### <a name="loyalty-programs"></a>Programy lojalnościowe

W kontekście cen i rabatów programy lojalnościowe są zasadniczo przynależnościami o specjalnych nazwach. Podobnie jak w przynależnościach, w programach lojalnościowych można ustawiać zarówno ceny, jak i rabaty. Jednak sposób, w jaki klienci otrzymują ceny z tytułu udziału w programie lojalnościowym podczas transakcji lub zamówienia, różnią się od sposobu, w jaki otrzymują ceny z tytułu przynależności. Klienci otrzymują ceny z tytułu udziału w programie lojalnościowym tylko w przypadku, gdy do transakcji jest dodana karta lojalnościowa. Po dodaniu karty lojalnościowej do transakcji jest również dodawany program lojalnościowy. Następnie program lojalnościowy umożliwia stosowanie specjalnych cen i rabatów.

Programy lojalnościowe mogą mieć wiele warstw, a rabaty mogą być różne dla różnych warstw. W ten sposób sprzedawcy detaliczni mogą przyznawać klientom większe korzyści bez konieczności ręczne umieszczania tych klientów w specjalnych grupach.

Programy lojalnościowe mają jeszcze dodatkowe funkcje, oprócz cen i rabatów. Jednak z punktu widzenia cen i rabatów są one takie same, jak mechanizm przynależności.

### <a name="catalogs"></a>Katalogi

Niektórzy sprzedawcy detaliczni używają fizycznych lub wirtualnych katalogów w celu reklamowania produktów i ustawiania cen dla określonych grup klientów. W ramach modelu biznesowego prowadzenia działań marketingowych za pośrednictwem katalogu sieci mogą ustawiać zróżnicowane ceny zależnie od katalogu. Microsoft Dynamics 365 obsługuje tę funkcjonalność, umożliwiając definiowanie rabatów i cen specyficznych dla katalogów, podobnie jak można definiować rabaty specyficzne dla kanałów lub przynależności. Podczas edytowania katalogu można skojarzyć grupy cenowe z katalogiem, tak jak można je skojarzyć z kanałem, przynależnością lub programem lojalnościowym.

### <a name="best-practices-for-price-groups"></a>Najlepsze praktyki dotyczące grup cenowych

Nie używaj tej samej grupy cenowej dla różnych typów jednostek. Zamiast tego należy używać jednego zestawu grup cenowych dla kanałów, innego zestawu grup cenowych dla przynależności lub programów lojalnościowych itd. Można użyć prefiksu lub sufiksu w nazwie grupy cenowej, aby wizualnie grupować różne typy używanych grup cenowych.

Unika ustawiania grup cenowych bezpośrednio dla odbiorców. Zamiast tego używaj przynależności. W ten sposób do odbiorców można przypisać wszystkie typy cen i rabatów, a nie tylko umowy handlowe na cenę sprzedaży.

## <a name="pricing-priority"></a>Priorytet cen

Priorytet cen jako obiekt składa się tylko z liczby i opisu. Priorytety cen mogą być stosowane do grup cenowych lub bezpośrednio do rabatów. Gdy są używane priorytety cen, umożliwiają one sprzedawcy detalicznemu zastąpienie zasady najlepszej ceny poprzez kontrolowanie kolejności, w jakiej ceny i rabaty są stosowane do produktów. Priorytet cen o wyższym numerze jest sprawdzany przed priorytetem cen o niższym numerze. Ponadto jeśli cena lub rabat zostaną znalezione w priorytecie o dowolnym numerze, wszystkie ceny i rabaty mające niższe numery priorytetu są ignorowane.

Cena i rabat mogą pochodzić z dwóch różnych priorytetów cen, ponieważ priorytety cen są stosowane do cen i rabatów niezależnie od siebie.

Aby użyć priorytetu cen dla cen, należy przypisać priorytet cen do grupy cenowej, a następnie utworzyć umowę handlową na cenę sprzedaży dla tej grupy cenowej.

Funkcja priorytetu cen została wprowadzona do obsługi scenariusza, gdzie sprzedawca detaliczny chce stosować wyższe ceny w określonej grupie sklepów. Na przykład sprzedawca detaliczny zdefiniował regionalne ceny dla wschodniego wybrzeża Stanów Zjednoczonych, ale chce wyższych cen dla niektórych produktów w sklepach w Nowym Jorku, ponieważ sprzedawanie produktów w tym mieście jest droższe i/lub lokalny rynek wytrzyma wyższą cenę.

Jak opisano w rozdziale „Najlepsza cena” w tym temacie, aparat kalkulacji cen zazwyczaj wybiera niższą z dwóch cen. Z tego względu sprzedawca detaliczny zwykle ma blokadę na użycie wyższej z dwóch cen w sklepie, który należy jednocześnie do grup cenowych Wschodnie wybrzeże i Nowy Jork. Aby rozwiązać ten problem przed wprowadzeniem funkcji priorytetu cen, sprzedawca detaliczny musiał dwa razy definiować ceny wszystkich produktów — nie mógł ich przypisać do grup cenowych. Alternatywnie sprzedawca detaliczny musiał tworzyć dodatkowe grupy cenowe w celu odizolowania produktów, które miały ceny wyższe niż standardowe, niższe ceny.

Natomiast funkcja priorytetu cen pozwala sprzedawcy detalicznemu utworzyć priorytet cen dla cen sklepowych wyższych niż określone w priorytecie cen dla cen regionalnych. Alternatywnie sprzedawca detaliczny może utworzyć priorytet cen tylko dla cen sklepowych, a ceny regionalne pozostawić z domyślnym priorytetem cen, który ma wartość 0 (zero). Obie konfiguracje pomagają zagwarantować, że ceny sklepowe zawsze będą używane przed cenami regionalnymi.

### <a name="pricing-priority-example"></a>Przykład priorytetu cen

Oto przykład, gdzie ceny sklepowe zastępują inne ceny.

Krajowy sprzedawca detaliczny ustawia większości cen według regionów i ma cztery regiony: Północny wschód, Południowy wschód, Środkowy zachód i Zachód. Zidentyfikował kilka rynków o wysokich kosztach, na których można by żądać wyższych cen. Te rynki to Nowy Jork, Chicago i obszar wokół Zatoki San Francisco.

W tym przykładzie przyjrzymy się dokładniej regionowi Północny wschód. Sklep 1 znajduje się w Bostonie, a sklep 2 na Manhattanie. W sklepie w Bostonie z kanałem są połączone dwie grupy cenowe: Północny wschód i Sklep 1. W sklepie na Manhattanie z kanałem są połączone trzy grupy cenowe: Północny wschód, NYC i Sklep 2.

Sprzedawca detaliczny konfiguruje maksymalnie dwa priorytety cen: Wysokie koszty ma priorytet o numerze 5, a Ceny sklepowe ma priorytet o numerze 10. (Należy pamiętać, że domyślnie priorytet cen jest równy 0 \[zero\], a ceny i rabaty o wyższym numerze priorytetu są używane przed cenami i rabatami o niższym numerze priorytetu). W grupie cenowej Północny wschód priorytet cen pozostawiono na wartości domyślnej **0** (zero). W grupie cenowej NYC priorytet cen ustawiono na **5**, ponieważ Nowy Jork jest rynkiem o najwyższych kosztach. W grupach cenowych Sklep 1 i Sklep 2 priorytet cen ustawiono na **10**.

Dwa produkty sprzedawane przez sprzedawcę detalicznego to produkt 1 — popularna koszulka, i produkt 2 — markowe spodnie.

| Produkt | Cena w grupie cenowej Północny wschód | Cena w grupie cenowej NYC | Cena sklepowa |
|---|---|---|---|
| Koszulka | 15 USD | Nie ustawiono | Nie ustawiono |
| Markowe spodnie | 50 USD | 70 USD | Nie ustawiono |

Koszulka jest sprzedawana w tej samej cenie (czyli 15 USD) w sklepach na Manhattanie i w Bostonie, ponieważ ustawiono tylko jedną cenę w grupie cenowej Północny wschód połączonej z oboma kanałami. Markowe spodnie są sprzedawane za 50 USD w sklepie w Bostonie, ponieważ jest to jedyna cena dostępna w tym sklepie. Jednak w sklepie na Manhattanie są dostępne dwie ceny: 50 USD i 70 USD. Ponieważ priorytet cen 5 dla grupy cenowej NYC jest wyższy niż priorytet 0 (zero) dla grupy cenowej Północny wschód, w systemie punktu sprzedaży będzie używana cena 70 USD.

> [!NOTE]
> Dla każdego priorytetu cen jest wymagane przejście przez całą logikę aparatu kalkulacji cen detalicznych. W związku z tym w celu zachowania odpowiedniej wydajności procesu obliczania cen i rabatów należy używać funkcji priorytetów cen tylko sporadycznie.

## <a name="types-of-prices"></a>Typy cen

W Microsoft Dynamics 365 cenę produktu można ustawić w trzech miejscach:

- Bezpośrednio w produkcie (cena podstawowa)
- W umowie handlowej na cenę sprzedaży
- W korekcie ceny

Cena podstawowa i cena w umowie handlowej należą do podstawowej funkcjonalności Dynamics 365 i są dostępne nawet wtedy, gdy nie używasz aplikacji Commerce. Funkcjonalność korekty ceny jest dostępna tylko w aplikacji Commerce. Następny rozdział zawiera więcej informacji na temat każdej z tych opcji ustawiania cen oraz wyjaśnia, jak opcje współpracują ze sobą.

## <a name="setting-prices"></a>Ustawienie cen

### <a name="base-price"></a>Podstawa ceny

Najłatwiejszym miejscem ustawiania ceny produktu jest sam produkt. Wartość ustawiona bezpośrednio w produkcie często jest nazywana ceną podstawową produktu. Cenę podstawową ustawia się w polu **Cena** na karcie **Sprzedaż** na stronie **Szczegóły zwolnionego produktu**. Wprowadzana wartość jest w walucie firmy. Domyślnie jest to cena za ilość 1 jednostki miary ustawionej w polu **Jednostka** na karcie **Sprzedaż**. Rzeczywista cena za jednostkę produktu zależy od jednostki miary, ilości dla ceny i waluty.

Jeśli produkt ma jedną cenę dla wszystkich klientów, cena podstawowa jest najbardziej efektywnym sposobem zarządzania ceną tego produktu. Nawet jeśli korzystasz z umów handlowych do wyznaczania ceny, warto również ustawić cenę podstawową w produkcie. Wtedy jeśli nie użyjesz umowy handlowej o zakresie **Wszystko**, masz awaryjną cenę, która zostanie użyta, gdy nie ma zastosowania żadna umowa handlowa.

Jeśli waluta w kanale różni się od waluty firmy, cena podstawowa w tym kanale będzie wyznacza poprzez konwersję waluty na cenie ustawionej w produkcie.

Mimo iż jednostka cenowa nie jest popularnym scenariuszem, aparat kalkulacji cen go obsługuje. Jeśli jednostka cenowa zostanie ustawiona na wartość inną niż **0** (zero), cena za jednostkę jest równa cenie podzielonej przez jednostkę cenową. Na przykład jeśli cena produktu wynosi 10,00 USD, a jednostka cenowa jest równa 50, cena za ilość 1 wynosi 0,20 USD (= 10,00 USD / 50).

### <a name="sales-price-trade-agreement"></a>Umowa handlowa na cenę sprzedaży

Za pomocą arkusza umów handlowych można tworzyć umowy handlowe na cenę sprzedaży dla każdego produktu. W Microsoft Dynamics 365 istnieją trzy zakresy odbiorców dla umów handlowych na cenę sprzedaży: **Tabela**, **Grupa** i **Wszystko**. Zakres odbiorców decyduje o odbiorcach, do których ma zastosowanie konkretna umowa handlowa na cenę sprzedaży.

Umowa handlowa na cenę sprzedaży o zakresie **Tabela** jest przeznaczona dla pojedynczego odbiorcy ustawionego bezpośrednio w umowie handlowej. Ten scenariusz nie jest typowym scenariuszem od firmy do konsumenta (B2C). Jednak jeśli wystąpi, aparat kalkulacji cen używa do wyznaczania ceny umów handlowych o zakresie **Tabela**.

Umowa handlowa na cenę sprzedaży o zakresie **Grupa** to typ najczęściej używany z funkcjami. Poza aplikacją Commerce umowy typu **Grupa** są stosowane do prostych grup odbiorców. Jednak w aplikacji Commerce koncepcja grupy odbiorców została rozszerzona i teraz jest bardziej ogólną grupą cenową. Grupę cenową można połączyć z kanałem, przynależnością, programem lojalnościowym lub katalogiem. Aby uzyskać szczegółowe informacje o grupach cenowych, zobacz rozdział „Grupy cenowe” wcześniej w tym temacie.

> [!NOTE]
> Cena z umowy handlowej jest zawsze używana przed ceną podstawową.

### <a name="price-adjustment"></a>Korekta ceny

Jak wskazuje nazwa, korekta ceny umożliwia zmodyfikowanie ceny, która została ustawiona bezpośrednio w produkcie albo za pośrednictwem umowy handlowej. Korekta ceny może służyć tylko obniżeniu ceny, a nie jej zwiększeniu. Korekta ceny to zalecany sposób, w jaki sprzedawcy detaliczni powinni tworzyć, śledzić i zarządzać obniżkami cen swoich produktów wraz z upływem czasu.

Istnieją są trzy typy korekt ceny: obniżka procentowa, obniżka kwotowa i cena. Korekta ceny typu obniżka procentowa lub obniżka kwotowa jest zawsze stosowana do transakcji sprzedaży. Natomiast korekta ceny typu cena jest stosowana tylko wtedy, gdy skorygowana cena jest niższa niż cena ustawiona za pomocą funkcji ceny podstawowej lub ceny w umowie handlowej. W związku z tym jeśli cena ustawiona w korekcie ceny jest wyższa od ceny nieskorygowanej, korekta ceny nie jest stosowana.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Wyznaczanie ceny produktu w transakcji

W obliczaniu ceny i rabatu w transakcji jest używana zasada znajdowania najlepszej ceny dla odbiorcy. Zgodnie z tą zasadą w przypadku znalezienia więcej niż jednej ceny jest stosowana najniższa cena. Ponadto jest używana kombinacja rabatów dająca największą kwotę rabatu dla całej transakcji. W niektórych przypadkach dla jednego produktu musi zostać użyty mniejszy rabat, tak aby można było zastosować dodatkowe rabaty do innych produktów w transakcji.

Jedyny wyjątek od tej zasady znajdowania najlepszej ceny dla odbiorcy to opcja najniższego rabatu łączonego. Ta opcja umożliwia stosowanie najniższych rabatów przy wybieraniu i grupowaniu produktów, co jest korzystne dla sprzedawcy detalicznego. W związku z tym jeśli transakcja obejmuje więcej produktów niż minimum wymagane do zastosowania najniższego rabatu, aparat kalkulacji cen wybiera produkty dające najmniejszy możliwy rabat dla odbiorcy.

Dla każdego produktu aparat kalkulacji cen zwraca trzy ceny: podstawową, z umowy handlowej i aktywną.

Cena podstawowa to po prostu właściwość produktu i jest taka sama wszędzie dla wszystkich odbiorców.

W umowie handlowej na cenę sprzedaży jeśli w opcji **Znajdź następny** ustawiono wartość **Tak**, to jako cena w umowie handlowej jest używana najniższa cena znaleziona w odnośnych umowach handlowych na cenę sprzedaży. Umowy handlowe można znaleźć przy użyciu grup cenowych lub kodu konta **Wszystko**. Alternatywnie umowy handlowe można przypisać bezpośrednio do odbiorców. Jeśli w opcji **Znajdź następny** ustawiono wartość **Nie**, jest używana pierwsza znaleziona cena z umowy handlowej. Jeśli nie zostaną znalezione żadne umowy handlowe na ceny sprzedaży, to cena w umowie handlowej jest ustawiana jako równa cenie podstawowej.

Aktywna cena jest obliczana poprzez wzięcie ceny z umowy handlowej i zastosowanie do niej największej korekty ceny dostępnej dla produktu. Jeśli nie zostaną znalezione żadne korekty cen lub jeśli obliczona cena aktywna jest wyższa niż cena w umowie handlowej, to aktywna cena jest ustawiana jako równa cenie w umowie handlowej. Należy pamiętać, że przy użyciu korekty ceny nie można podnieść ceny produktu. Korekty cen mające zastosowanie można znaleźć tylko przy użyciu grup cenowych, które są przypisane do kanału, katalogu, przynależności lub programu lojalnościowego.

## <a name="category-price-rules"></a>Reguły cen dla kategorii

Funkcja reguł cen dla kategorii w aplikacji Commerce umożliwia łatwe tworzenie nowych umów handlowych dla wszystkich produktów w kategorii. Ta funkcja umożliwia również automatyczne wyszukiwanie istniejących umów handlowych dla produktów należących do kategorii i ich unieważnianie (wygaszanie).

Po wybraniu opcji unieważniania istniejących umów handlowych system utworzy nowy arkusz umów handlowych dla produktów w kategorii, które mają aktywne umowy handlowe. Jednak arkusz należy zaksięgować ręcznie. Ponadto reguły cen dla kategorii umożliwiają znajdowanie istniejących umów handlowych tylko wtedy, gdy używasz tej samej reguły cen (to znaczy jeśli utworzysz nową regułę cen, która wykorzystuje tę samą kategorię, co poprzednio). Jeśli nie używasz tej samej reguły cen, istniejąca umowa handlowa nie wygaśnie.

Ceny można zwiększać i zmniejszać za pomocą pól **Reguła ceny** i **Podstawa ceny** w regułach cen dla kategorii.

- W polu **Reguła ceny** wybierz typ zmiany ceny, który ma zostać użyty:

    - **Narzut** — Procent podstawy ceny jest używany do obliczania ceny sprzedaży. Na przykład produkt, który sprzedaje się za 15,00, a kosztuje 10,00, ma 50 procent narzutu.
    - **Marża** — Procent ceny sprzedaży jest używany do obliczania kwoty zysku. Na przykład Produkt, który sprzedaje się za 15,00, a kosztuje 10,00, ma 33,3 procent marży.
    - **Stała kwota** — Kwota dodana do podstawy ceny jest używana do obliczania ceny sprzedaży. Na przykład Produkt, który sprzedaje się za 15,00 i kosztuje 10,00, ma stałą kwotę 5,00.

- W polu **Podstawa ceny** wybierz typ ceny, który chcesz zmodyfikować:

    - **Koszt podstawowy** — Kwota, jaką sprzedawca detaliczny zapłacił dostawcy.
    - **Podstawa ceny** — Cena sprzedaży przed zastosowaniem umów handlowych i korekt ceny.
    - **Bieżąca cena** — Cena sprzedaży po zastosowaniu umów handlowych i korekt ceny.

Aby łatwo aktualizować ceny różnych produktów należących do różnych kategorii produktów, można używać uzupełniających kategorii produktów razem z regułami cen dla kategorii.

## <a name="best-practices"></a>Najlepsze praktyki

Microsoft SQL Server Express jest często używane dla baz danych kanałów ze względu na koszty (jest darmowy). Należy pamiętać, że program SQL Server Express ma ograniczenia sprzętowe i ograniczenia dotyczące rozmiaru danych. Przy złym planowaniu można szybko wyczerpać limity rozmiaru danych programu SQL Server Express. Uwagi te odnoszą się nie tylko do cen, ale również do innych obszarów produktu. Poniżej przedstawiono kilka najlepszych praktyk, które mogą pomóc zmniejszyć rozmiar danych:

- Jeśli korzystasz z umów handlowych, po zmianie cen należy wygasić stare umowy handlowe, ustawiając dla nich datę końcową. To rozwiązanie pomaga zmniejszyć liczbę umów handlowych tworzonych wraz z upływem czasu, które są przechowywane w bazach danych kanałów. Pomaga również zmniejszyć ilość danych, z którymi musi pracować algorytm obliczania cen.
- Jeśli ceny są różne dla wariantów produktu, rozważ używanie ceny podstawowej produktu jako ceny najpopularniejszego wariantu. Następnie używaj umów handlowych tylko do cen wariantów, które są wyjątkami. Ta metoda umożliwia zredukowanie liczby rekordów umów handlowych. Ponieważ bardzo łatwo jest importować dane do Microsoft Dynamics 365, może się pojawić pokusa zaimportowania umowy handlowej dla każdego wariantu każdego produktu. Jednak takie podejście może spowodować powstanie wielu umów handlowych mających tę samą wartość. W związku z tym niepotrzebnie zwiększy to ilość zgromadzonych danych.
- Aplikacja Commerce przetwarza ceny specyficzne dla wariantów w kolejności od najbardziej do najmniej specyficznych. Jeśli wymiar produktu nie ma wpływu na cenę, nie trzeba dla niego definiować umów handlowych. Na przykład produkt jest dostępny w trzech kolorach i czterech rozmiarach, jednak cena różni się tylko w zależności od rozmiaru. Jeśli zdefiniujesz umowę handlową dla każdego wariantu, utworzysz 12 rekordów. Zamiast tego lepiej zdefiniować umowę handlową tylko dla każdego rozmiaru, a pole wymiaru Kolor pozostawić puste. W takim przypadku powstaną tylko cztery rekordy.

    Alternatywnie, jeśli nie każda wartość wymiaru skutkuje inną ceną, można zdefiniować jedną umowę handlową dla produktu głównego, a wszystkie wymiary produktu pozostawić puste. Następnie można zdefiniować osobną umowę handlową tylko dla każdej wartości wymiaru, która powoduje inną cenę. Na przykład jeśli rozmiar XXL ma wyższą cenę, ale wszystkie pozostałe rozmiary mają taką samą cenę, potrzebujesz tylko dwóch umów handlowych: jedną dla produktu głównego i jedną dla rozmiaru XXL.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Cen zawierające podatek a ceny bez podatku

Podczas ustawiania cen sprzedaży w Dynamics 365 nie określasz, czy wprowadzana wartość ceny obejmuje podatek, czy nie. Wartość mówi ogólnie o cenie. Jednak ustawienie **Cena zawiera podatek** dostępne w kanałach pozwala skonfigurować kanały, tak aby uwzględniały lub nie uwzględniały podatku w cenach. To ustawienie konfiguruje się w kanale i może przybierać różne wartości nawet w jednej firmie.

Jeśli pracujesz z cenami zawierającymi, jak i niezawierającymi podatku, jest bardzo ważne, aby poprawnie ustawić ceny, ponieważ łączna kwota płacona przez odbiorcę zmieni się, jeżeli w kanale zmienisz wartość ustawienia **Cena zawiera podatek**.

## <a name="differences-between-retail-pricing-and-non-retail-pricing"></a>Różnice między cenami detalicznymi a cenami niezwiązanymi z handlem detalicznym

Jeden aparat kalkulacji cen jest używany do obliczania cen we wszystkich kanałach: biura obsługi, sklepów sieci sprzedaży (tradycyjnych) i sklepów internetowych. Pomaga to realizować ujednolicone scenariusze handlu.

Ceny są przeznaczone do używania z jednostkami handlu detalicznego, a nie jednostkami niezwiązanymi z handlem detalicznym. W szczególności służą do ustawiania cen w sklepach, a nie w magazynach.

Aparat kalkulacji cen **nie obsługuje** następujących funkcji cen:

- Ustawianie cen według wymiarów magazynowania typu Oddział lub Oddział i magazyn nie jest obsługiwane. Jeśli określisz tylko wymiar oddziału w umowach handlowych, aparat kalkulacji cen zignoruje Oddział i zastosują umowę handlową do wszystkich oddziałów. Jeśli określisz oddział i magazyn, to zachowanie jest niezdefiniowane/niesprawdzone, ponieważ oczekuje się, że sprzedawcy detaliczni używają grup cenowych sklepu do kontrolowania cen dla każdego sklepu/magazynu.
- Kalkulacja cen oparta na atrybutach nie jest obsługiwana.
- Przekazywanie rabatu dostawcy nie jest obsługiwane.
- Standardowy aparat cenowy Supply Chain Management obsługuje obliczanie cen na podstawie „Żądanej daty wysyłki” i „Żądanej daty przyjęcia” wraz z bieżącą datą. Jednak ceny detaliczne nie obsługują obecnie tych wartości. Powodem jest to, że w scenariuszach B2C klienci nie oczekują, że żądana data dostawy ma wpływ na cenę towaru. W niektórych przypadkach detaliści prowadzą zarówno operacje typu B2B, jak i B2C. W przypadku operacji B2B wspólne ceny są zmieniane na podstawie dat dostawy. Detaliści ci mogą korzystać z cen Supply Chain Management dla swojej działalności B2B oraz cen detalicznych dla swojej działalności B2C. Ceny detaliczne zostaną uruchomione tylko wtedy, gdy użytkownik aplikacji zostanie dodany jako użytkownik centrum telefonicznego, dzięki czemu detaliści mogą przypisać określonych użytkowników, którzy będą pracować z cenami Supply Chain Management i przypisać kilku, którzy będą pracować z cenami detalicznymi, to znaczy tych użytkowników należy dodać jako użytkowników w biurze obsługi. Ponadto musi być włączona właściwośc **Użyj dzisiejszej daty do obliczenia cen** w sekcji **Parametry Commerce > ceny i rabaty > Różne**. W ten sposób można przechowywać wartość parametru rozrachunków z odbiorcami dla żądanej daty wysyłki lub żądanej daty odbioru dla cen Supply Chain Management, ale ceny detaliczne będą nadal używane przy obliczaniu cen w dzisiejszej dacie.

Ponadto **tylko** aparat kalkulacji cen obsługuje następujące funkcje cen:

- Cena bazuje na wymiarach produktów, w kolejności od ceny najbardziej specyficznej dla wariantu, przez najmniej specyficzną dla wariantu, aż do ceny produktu głównego. Cena ustawiana za pomocą dwóch wymiarów produktu (na przykład Kolor i Rozmiar) jest wykorzystywana przed ceną ustawianą za pomocą tylko jednego wymiaru produktu (np. Rozmiar).
- Jedna grupa cenowa może służyć do kontrolowania cen i rabatów.

## <a name="pricing-api-enhancements"></a>Udoskonalenia interfejsu API ustalania cen

Cena jest jednym z najważniejszych czynników kontrolujących decyzje dotyczące kupowania wielu odbiorców, a wielu z nich przed dokonaniem zakupu porównuje ceny w różnych oddziałach. Aby zapewnić konkurencyjne ceny, detaliści uważnie obserwują swoich konkurentów i często organizują promocje. Dlatego też, aby ułatwić tym detalistom przyciąganie odbiorców, bardzo ważne jest, by w wyszukiwaniu produktów, funkcja przeglądania, listy i strona szczegółów produktów pokazywały najbardziej dokładne ceny.

W nadchodzącej wersji modułu Commerce interfejs programowania aplikacji (API) **GetActivePrices** będzie zwracał ceny obejmujące rabaty proste (np. rabaty jednowierszowe niezależne od innych towarów w koszyku). W ten sposób wyświetlane ceny są zbliżone do rzeczywistej kwoty, jaką odbiorcy zapłacą za towary. Ten interfejs API będzie uwzględniał wszystkie typy rabatów prostych: oparte na przynależności, lojalnościowe, oparte na katalogach i oparte na kanałach. Ponadto interfejs API zwróci nazwy i informacje o ważności dla zastosowanych rabatów, dzięki czemu sprzedawcy detaliczni będą mogli dostarczać bardziej szczegółowy opis ceny i zachęcać do pośpiechu, jeśli ważność rabatu ma wkrótce wygasnąć.


[!INCLUDE[footer-include](../includes/footer-banner.md)]