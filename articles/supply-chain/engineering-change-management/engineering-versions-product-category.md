---
title: Wersje inżynieryjne i kategorie produktów inżynieryjnych
description: Ten temat zawiera informacje dotyczące pojęć związanych z wersjami inżynieryjnymi. Wersje inżynieryjne zapewniają, że różne stany produktu i jego danych są aktualne i przejrzyste oraz że można je wizualizować w systemie.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 3eb5b5c4304b393008ecc5f5ff5a663295ed0d22
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435670"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Wersje inżynieryjne i kategorie produktów inżynieryjnych

[!include [banner](../includes/banner.md)]

Produkty inżynieryjne ewoluują w trakcie ich cyklu życia z wielu powodów. Na przykład, zmiany mogą zostać wprowadzone w celu poprawy serwisowania produktu, zmiany składnika, ponieważ dostawca już go nie oferuje, reagowania na nowe spostrzeżenia lub naprawiania błędów w początkowym projekcie. Istnieje również wiele powodów, dla których te zmiany powinny być przechowywane jako część trwającego produktu, w taki sposób, aby poprzednie dane nie zostały nadpisane. Oto niektóre z tych powodów:

- Chcesz śledzić produkt, który został wyprodukowany i dostarczony do klientów w poprzednich stanach cyklu życia.
- Potrzebujesz czasu na zatwierdzenie i zastosowanie zmian.
- Chcesz mieć sygnaturę czasową każdej zmiany i chcesz mieć możliwość dostarczania wcześniej wyprodukowanych produktów oddzielnie od siebie.

*Wersje inżynieryjne* zapewniają, że różne stany produktu i jego danych są aktualne i przejrzyste oraz że można je wizualizować w systemie. Ta koncepcja pomaga w utrzymaniu spójności, blokowaniu BOM dla produkcji, eliminacji zmienności i łatwej identyfikacji zmian.

Zazwyczaj reguła *kształt-dopasowanie-funkcja* jest stosowana do określenia, czy zmiana wymaga nowego produktu, nowej wersji czy aktualizacji istniejącej wersji. Każdy z trzech terminów w nazwie tej reguły odnosi się do określonego aspektu części, co pomaga inżynierom dopasować części do potrzeb. Zasada kształt-dopasowanie-funkcja zwiększa elastyczność zmian projektowych, ponieważ zmiana części wymaga minimalnej dokumentacji i kosztów projektu, pod warunkiem zachowania dopasowania, kształtu i funkcji produktu.

- **Dopasowanie** odnosi się do zdolności części lub funkcji do łączenia się z innymi funkcjami lub dopasowania do innych funkcji lub części w zestawie. Dopasowanie umożliwia części spełnianie wymaganych tolerancji montażowych, dzięki czemu może być użyteczna.
- **Kształt** odnosi się do charakterystyk części lub zestawu, takich jak wymiary zewnętrzne, waga, rozmiar i wygląd wizualny. Kształt jest aspektem, który najbardziej zależy od wyboru estetyki przez inżyniera. Obejmuje obudowę, podstawę montażową i panel sterowania, które stają się zewnętrzną „twarz” produktu.
- **Funkcja** to kryterium, które jest spełnione, gdy część skutecznie i niezawodnie spełnia swoje zadanie. Na przykład w produkcie elektronicznym funkcja może zależeć od użytych komponentów półprzewodnikowych oraz oprogramowania lub oprogramowania układowego. Często może to również zależeć od cech wybranej obudowy. Dwa z najczęstszych powodów, dla których obudowa może nie spełnić kryterium funkcji, to źle umiejscowione lub źle dobrane porty oraz mylące lub brakujące etykiety. 

## <a name="engineering-versions"></a>Wersje projektowe

Kiedy używasz produktów inżynierskich, każdy produkt ma co najmniej jedną wersję inżynierską. Początkowa wersja inżynierska jest tworzona automatycznie podczas tworzenia produktu inżynieryjnego. Każda wersja inżynieryjna przechowuje dane techniczne, które są specyficzne dla tej wersji. Oto kilka przykładów takich danych:

- Numer wersji i poprzedni numer wersji (w razie potrzeby)
- Daty początku i końca obowiązywania
- Status aktywnej wersji produktu, który wskazuje, czy wersję można zwolnić i używać w transakcjach (Więcej informacji zawiera sekcja [Gotowość produktu](product-readiness.md).)
- Firma inżynieryjna, która stworzyła produkt i jest jego właścicielem (aby uzyskać więcej informacji, zobacz [Reguły dotyczące firm inżynieryjnych i własności danych](engineering-org-data-ownership-rules.md).)
- Powiązane dokumenty inżynieryjne, takie jak instrukcja montażu, instrukcje użytkownika, zdjęcia i łącza
- Atrybuty inżynieryjne (więcej informacji znajdziesz w [Atrybuty inżynieryjne i wyszukiwanie atrybutów inżynieryjnych](engineering-attributes-and-search.md)).
- BOM inżynieryjne
- Marszruty inżynieryjne

Możesz zaktualizować te dane w istniejącej wersji lub utworzyć nową wersję, używając *zlecenia zmiany inżynieryjnej*. (Aby uzyskać więcej informacji, należy zapoznać się z tematem [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).) W przypadku utworzenia nowej wersji produktu system skopiuje wszystkie dane związane z konstrukcją techniczną do nowej wersji. Następnie można zmodyfikować dane dla nowej wersji. W ten sposób możesz śledzić określone dane dla każdej kolejnej wersji. Aby porównać różnice między kolejnymi wersjami inżynieryjnymi, sprawdź kolejność zmian inżynieryjnych, która obejmuje typy zmian, które wskazują wszystkie zmiany.

Jak wspomniano wcześniej, początkowa wersja inżynierska jest tworzona automatycznie podczas tworzenia produktu inżynieryjnego. Numer wersji dla tej wersji jest zgodny z regułą dotyczącą numeru wersji zdefiniowaną w kategorii inżynieryjnej produktu. Aby przejść do kolejnej wersji, należy dodać produkt do zlecenia zmiany inżynieryjnej jako linię i ustawić pole **Wpływ** na *Nowa wersja*. Zlecenie zmiany inżynieryjnej będzie zawierało szczegóły zmiany z bieżącej wersji na następną.

Należy pamiętać, że produkt inżynieryjny może być objęty tylko jednym zleceniem zmian technicznych naraz. To ograniczenie zapewnia dokładność danych i pomaga uniknąć nakładania się lub sprzecznych zmian w produkcie. Należy zauważyć, że pole **Inżynier** w widoku **Nagłówek** zlecenia zmiany inżynieryjnej pokazuje inżyniera, który jest odpowiedzialny za zlecenie zmiany inżynieryjnej. Jeśli inżynier należy do zespołu, który jest zdefiniowany w systemie, pole **Odpowiedzialna osoba** pokazuje lidera tego zespołu.

## <a name="track-versions-in-transactions"></a>Śledź wersje w transakcjach

W przypadku korzystania z zarządzania zmianami inżynieryjnymi dane podstawowe produktu zawsze obejmują jedną lub więcej wersji inżynieryjnych. W ustawieniach produktów inżynieryjnych można określić, czy wersja inżynieryjna jest również częścią *transakcji logistycznych*. (Aby uzyskać więcej informacji, należy zapoznać się z sekcją [Skonfiguruj kategorie produktów inżynieryjnych](#product-category) w dalszej części tego tematu). Jeśli wpływ logistyczny jest istotny, różni się w zależności od produktu i firmy. Czasami jest używana tylko najnowsza wersja produktu. Dlatego po wprowadzeniu nowej wersji nie można już używać poprzedniej wersji. W innych przypadkach poprzednia wersja jest wymagana w transakcjach logistycznych, aby sprostać następującym wyzwaniom:

- Dział logistyki musi wysłać klientowi dwie sztuki produktu. W takim przypadku musisz zdecydować, czy chcesz, czy pozwolisz na wysłanie dwóch różnych wersji.
- Później odkryto, że pojawił się problem i że jest on związany z określoną zmianą. W takim przypadku korzystne może być dokładne określenie, która wersja została dostarczona w każdym zamówieniu.
- Firmy zazwyczaj chcą najpierw wysłać stare wersje, aby wycofać je z magazynu. Podejście to często można zarządzać, szczególnie w przypadku produktów o niewielkich nakładach, określając daty obowiązywania nowej wersji w odniesieniu do prognoz dotyczących wyczerpania zapasów starej wersji. Czasami jednak możesz nie być w stanie dokonać tego porównania lub możesz uznać, że niepewność prognoz dotyczących poziomu akcji jest zbyt wysoka.

Decyzja o tym, czy wersje mają być widoczne w inwentarzu, zależy od czynników, takich jak te, które zostały wcześniej wspomniane, a także praktyki firmy i innych czynników specyficznych dla każdej firmy. Istnieje możliwość określenia zachowania *kategorii produktów inżynieryjnych*. Będzie to miało zastosowanie do wszystkich produktów utworzonych z tej kategorii, dla wszystkich firm, do których produkt jest wydawany.

W przypadku produktów skonfigurowanych tak, aby miały wpływ logistyczny, wersję inżynieryjną należy określić w każdej transakcji. Mimo że system zaproponuje *najnowszą aktywną wersję*, można wybrać spośród wszystkich aktywnych wersji dostępnych dla danej firmy. W przypadku produktów, które są skonfigurowane tak, aby nie miały wpływu logistycznego, wersja inżynierska nie jest określana w transakcjach. Jednak system używa najnowszej wersji aktywnej. Na przykład po dodaniu produktu do produkcyjnego BOMu zostanie użyta najnowsza wersja, a po uruchomieniu planowania głównego zostanie przyjęta najnowsza wersja.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Skonfiguruj kategorie produktów inżynieryjnych

Kategoria produktów inżynieryjnych stanowi podstawę do tworzenia konkretnego produktu inżynieryjnego. Każda kategoria ustanawia zbiór wartości domyślnych i zasad. Dlatego tworząc produkt inżynieryjny, najpierw należy wybrać kategorię, z której zostanie utworzony.

Należy pamiętać, że nowy typ hierarchii kategorii (*hierarchia produktów inżynieryjnych*) jest automatycznie ustawiany dla użytkownika. Kategorie można tworzyć ręcznie, przechodząc do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Szczegóły kategorii produktów inżynieryjnych**.

Każda kategoria produktów inżynieryjnych określa domyślne zachowanie produktów inżynieryjnych, które są tworzone na podstawie tej kategorii. Po utworzeniu produktu inżynieryjnego nie możesz zmienić jego kategorii produktów inżynieryjnych. Jeśli jednak wybierzesz niewłaściwą kategorię, możesz usunąć produkt, a następnie utworzyć go ponownie.

Po utworzeniu kategorii produktów inżynieryjnych nie można zmienić następujących ustawień:

- Firma inżynieryjna
- Typ produktu
- Podtyp produktu
- Grupa wymiarów produktu
- Technologia konfiguracji
- Reguła numeru wersji

Inne ustawienia mogą dziedziczyć wartości domyślne skonfigurowane dla kategorii produktów inżynieryjnych. Jednak zgodnie z regułami systemu wartości te można zmieniać.

Aby pracować z kategoriami produktów inżynieryjnych, przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Szczegóły kategorii produktów inżynieryjnych**. Następnie wykonaj jeden z następujących kroków.

- Aby utworzyć nową kategorię, wybierz opcję **Nowa** w okienku akcji, a następnie określ te pola zgodnie z poniższymi podsekcjami.
- Aby edytować istniejącą kategorię, wybierz ją w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie określ pola w sposób opisany w poniższych podsekcjach.
- Aby usunąć istniejący zestaw kategorii, zaznacz je w okienku listy, a następnie wybierz **Usuń** w okienku akcji.

### <a name="header"></a>Nagłówek

Ustaw następujące pola w nagłówku kategorii produktów inżynieryjnych.

| Pole | opis |
|---|---|
| Imię i nazwisko | Służy do wprowadzania nazwy dla kategorii produktu. |
| Firma inżynieryjna | Wybierz firmę inżynieryjną, w której można tworzyć produkty z tej kategorii produktów inżynieryjnych i gdzie będą one konserwowane. |

### <a name="details-fasttab"></a>Skrócona karta Szczegóły

Ustaw następujące pola na skróconej karcie **Szczegóły** kategorii produktów inżynieryjnych.

| Pole | opis |
|---|---|
| Typ produktu | Określ, czy kategoria dotyczy produktów lub usług. |
| Śledź wersje w transakcjach | Wybierz, czy wersja produktu powinna być stemplowana na wszystkich transakcjach (wpływ logistyczny). Na przykład, jeśli śledzisz wersję w transakcjach, każde zamówienie sprzedaży pokaże, która konkretna wersja produktu została sprzedana w tym zamówieniu sprzedaży. Jeśli nie śledzisz wersji w transakcjach, zamówienia sprzedaży nie pokażą, która konkretna wersja została sprzedana. Zamiast tego zawsze pokazuje najnowszą wersję.<ul><li>Jeśli ta opcja ma wartość *Tak*, dla produktu jest tworzony produkt główny, a każda wersja produktu będzie wariantem korzystającym z wymiaru produktu *wersja*. Pole **Podtyp produktu** jest automatycznie ustawiane na *Produkt główny* i należy wybrać grupę wymiarów produktu, w której jest aktywny wymiar *wersji*. Wyświetlone zostaną tylko grupy wymiarów produktów, w których *wersja* jest aktywnym wymiarem. Aby utworzyć nowe grupy wymiarów produktu, należy wybrać przycisk **Edytuj** (symbol ołówka).</li><li>Jeślo ta opcja jest ustawiona na *Nie*, wymiar produktu *wersja* nie zostanie użyty. Następnie możesz wybrać, czy chcesz utworzyć produkt lub produkt główny, który używa innych wymiarów.</li></ul><p>Ta opcja jest często używana w przypadku produktów, które mają różnicę kosztów między wersjami lub produktów, w przypadku których obowiązują inne warunki w odniesieniu do klienta. Dlatego ważne jest, aby wskazać, która wersja została użyta w każdej transakcji.</p> |
| Podtyp produktu | Wybierz, czy kategoria będzie zawierać produkty, czy wzorce produktów. W przypadku produktów głównych będą używane wymiary produktu.
| Grupa wymiarów produktu | Wersje **Śledź wersje w transakcjach** pomagają w wybraniu podtypu produktu. Jeśli określono, że chcesz śledzić wersję w transakcjach, zostaną wyświetlone grupy wymiarów produktu, w których jest używany wymiar *wersji*. W przeciwnym razie zostaną wyświetlone tylko grupy wymiarów produktów, w których wymiar *wersja* nie jest używany. |
| Tworzenie stanu cyklu życia produktu | Skonfiguruj domyślny stan cyklu życia produktu, który powinien mieć produkt inżynieryjny podczas pierwszego tworzenia. Aby uzyskać więcej informacji, zobacz [Stany cyklu życia produktu i transakcje](product-lifecycle-state-transactions.md). |
| Reguła numeru wersji | Wybierz regułę numeru wersji, która ma zastosowanie do kategorii:<ul><li>**Ręczna** — w tym celu należy wybrać numer wersji dla każdej nowej wersji.</li><li>**Automatycznie** — System ustawia numer wersji na podstawie zdefiniowanego formatu. Podczas konfigurowania formatu należy zastosować znak numeru (\#), który reprezentuje cyfrę i dowolny inny znak reprezentujący stałą wartość. Na przykład, jeśli zdefiniujesz format jako *V-\#\#*, pierwszą wersją będzie „V-01”, drugą - „V-02” i tak dalej.</li><li>**Lista** — System pobiera kolejną liczbę z predefiniowanej listy wartości niestandardowych, które zdefiniujesz.</li></ul> |
| Wymuś obowiązywanie | Wybierz, czy daty obowiązywania wersji inżynieryjnych muszą być ciągłe, czy też mogą występować przerwy i nakładanie się. To ustawienie ma wpływ na sposób, w jaki można używać pól **Obowiązuje od** i **Obowiązuje do** dla każdej wersji inżynierskiej, do której ma zastosowanie kategoria.<ul><li>Jeśli ta opcja jest ustawiona na wartość *Tak*, dla każdej wersji musi być określona efektywna wartość **Obowiązuje od**, a między wersjami nie są dozwolone pokrywanie się dat ani przerwy. Zakres dat dla każdej wersji inżynierskiej jest bezpośrednio połączony z poprzednią i następną wersją techniczną, jeśli takie istnieją. W tym scenariuszu zawsze używana jest najnowsza wersja, a starsze wersje nie są już używane.</li><li>Jeśli ta opcja jest ustawiona na **Nie**, nie ma ograniczeń co do pól daty obowiązywania dla wersji inżynieryjnych i dozwolone są zarówno pokrywanie się dat, jak i przerwy. W tym scenariuszu wiele wersji może być aktywnych w tym samym czasie i możesz pracować z dowolną aktywną wersją.</li></ul><p>Ta opcja ma również wpływ na specyfikacje BOM i marszruty, które są połączone z wersją produktu. Aby uzyskać więcej informacji, zobacz sekcję [Łączenie BOM i marszrut z wersjami inżynierskimi](#boms-routes) w dalszej części tego tematu.</p> |
| Użyj nazewnictwa reguły identyfikatora | Ustaw tę opcję na *Tak*, aby włączyć reguły definiowania numeru produktu przy użyciu sekwencji numerów, nazw i wartości atrybutów inżynieryjnych oraz stałych tekstowych jako segmentów. Aby utworzyć lub zmodyfikować reguły, wybierz przycisk **Edytuj**. |
| Użyj nazewnictwa reguły nazwy | Ustaw tę opcję na *Tak*, aby włączyć reguły definiowania nazwy przy użyciu nazw atrybutów inżynieryjnych, wartości atrybutów inżynieryjnych i stałych tekstowych jako segmentów. Aby utworzyć lub zmodyfikować reguły, wybierz przycisk **Edytuj**. |
| Użyj nazewnictwa reguły opisu | Ustaw tę opcję na *Tak*, aby włączyć reguły definiowania opisu przy użyciu nazw atrybutów inżynieryjnych, wartości atrybutów inżynieryjnych i stałych tekstowych jako segmentów. Aby utworzyć lub zmodyfikować reguły, wybierz przycisk **Edytuj**. |

### <a name="attributes-fasttab"></a>Skrócona karta Atrybuty

Korzystając z siatki na skróconej karcie **Atrybuty**, można skonfigurować atrybuty inżynieryjne stosowane do produktów należących do tej kategorii. Aby uzyskać więcej informacji o tworzeniu atrybutów inżynieryjnych, zapoznaj się z [Atrybuty inżynieryjne i wyszukiwanie atrybutów inżynieryjnych](engineering-attributes-and-search.md).

Przyciski na skróconej karcie **Atrybuty** służą do dodawania, usuwania i rozmieszczania atrybutów w siatce.

Jeśli zmienisz wybór atrybutów dla kategorii inżynieryjnej, a produkty oparte na tej kategorii już istnieją, musisz zdecydować, czy zastosować zmiany do tych produktów. Jeśli chcesz, aby istniejące produkty odzwierciedlały zmiany, wybierz opcję **Aktualizuj istniejące produkty** na skróconej karcie **Atrybuty**.

Dla każdego dodawanego wiersza do siatki należy określić następujące pola:

| Pole | opis |
|---|---|
| Imię i nazwisko | Zaznacz atrybuty do dodania. |
| Wartość | Wybierz domyślną wartość atrybutu. |
| Wymagany | W przypadku atrybutów typu *Wartość logiczna*, jeśli ta opcja ma wartość *Tak*, użytkownicy muszą nadać atrybutowi wartość *Tak*. Jeśli ta opcja ma wartość *Nie*, użytkownicy mogą ustawiać atrybut na wartość *Tak* lub *Nie*. W przypadku innych typów danych ustawienie tej opcji ma charakter informacyjny. |
| Atrybut partii | Wybierz, czy atrybut ma być propagowany za pomocą funkcji wsadowej. |

### <a name="readiness-policy-fasttab"></a>Skrócona karta Zasady gotowości

Aby wybrać zasady gotowości dotyczące produktów należących do tej kategorii, należy skorzystać z pola **Zasady gotowości produktów**. Aby uzyskać więcej informacji, zobacz temat [Gotowość produktu](product-readiness.md).

### <a name="release-policy-fasttab"></a>Skrócona karta Zasady zwalniania

Aby wybrać zasady zwalniania produktów należących do tej kategorii, należy skorzystać z pola **Zasady zwalniania produktów**. Aby uzyskać więcej informacji, zobacz [Zwalnianie struktur produktu](release-product-structure.md).

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Łączenie BOM i marszrut z wersjami inżynieryjnymi

Ustawienie opcji **Wymuszaj efektywność** jest ważne ze względu na połączenie BOM i marszrut z ich wersjami inżynieryjnymi. Możesz aktywować wiele BOMów lub marszrut na produkt tylko wtedy, gdy występuje różnica w którymkolwiek z następujących ustawień:

- Wymiar produktu
- Ilość
- Oddział
- Daty obowiązywania

Inżynieryjne BOM i marszruty są tworzone z wersji inżynieryjnej, w której mają zastosowanie. Mogą one być rozpoznawane przez znacznik wyboru w polu wyboru **Kontrolowane przez dane inżynieryjne**. Podczas pracy z BOM i marszrutami inżynieryjnymi nie można ich zwykle projektować przy użyciu różnych ilości. Nie można też zwykle projektować różnych BOM według oddziałów. Ponadto dla inżynieryjnych BOM i marszrut daty obowiązywania są zawsze pobierane z wersji inżynieryjnej. Dlatego wersja inżynieryjna, jej BOM i marszruta będą miały takie same daty obowiązywania.

W przypadku produktów, w których używasz wymiaru *wersji* produktu (wraz z logistycznym wpływem na transakcje), wersja jest również dodawana do BOM i marszrut. To zachowanie ułatwia rozróżnianie BOM i marszrut z kolejnymi wersjami niezależnie od ustawienia **Wymuszaj efektywność**.

W przypadku produktów, w których nie używasz wymiaru *wersji* produktu (bez logistycznego wpływu na transakcje), wersja nie jest dodawana do BOM ani marszrut. Z tego powodu nie będzie różnic między BOM i marszrutami kolejnych wersji. W takim przypadku zdecydowanie zaleca się ustawienie opcji **Wymuszaj efektywność** na wartość *Tak*. W ten sposób można zapobiec nakładaniu się wersji inżynierskich, a także aktywować zestawienie komponentów i marszrutę nowszej wersji bez konieczności uprzedniej dezaktywacji zestawienia komponentów i marszruty poprzedniej wersji. Jeśli w tym przypadku ustawienie opcji **Wymuszaj efektywność** wartość *Tak*, należy ręcznie dezaktywować BOM i marszruty w starszych wersjach, aby umożliwić aktywację najnowszej wersji.
