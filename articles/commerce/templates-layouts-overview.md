---
title: Omówienie szablonów i układów
description: Ten temat obejmuje szablony i układy w Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 835b283ea93f761791745a41c74b6a12c11eea02
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962967"
---
# <a name="templates-and-layouts-overview"></a>Omówienie szablonów i układów


[!include [banner](includes/banner.md)]

Szablony są podstawą modelu strony Microsoft Dynamics 365 Commerce. Jeśli celem jest maksymalizacja wydajności i spójności przepływów pracy tworzenia witryn, ważne jest, aby dowiedzieć się, jak korzystać z zalet szablonów serwisu www. Wczesne decyzje dotyczące struktury szablonów są istotne i mogą znacząco wpływać na koszty i dynamikę codziennych, sezonowych i ważnych aktualizacji marki. Dobrza struktura szablonów ma również inne zalety. Na przykład ułatwiają one ulepszanie wyników optymalizacji aparatu wyszukiwania (SEO) w całej witrynie oraz minimalizację liczby usterek.

Dobrym sposobem na rozpoczęcie pracy z szablonami jest zrozumienie funkcjonalnych zalet szablonów i układów, różnic między nimi i hierarchii.

Na poniższej ilustracji przedstawiono hierarchię modelu stron za wyrenderowaną stroną sieci Web.

![Diagram modelu strony](../commerce/media/page-model-diagram.png)

| Jednostka        | Podstawowea funkcja |
|---------------|----------------|
| Szablon      | Szablony definiują opcje modułu i podstawowe rusztowania dla zbioru układów i instancji stron. |
| Układ        | Układy służą do definiowania ostatecznego wyboru i rozmieszczenia modułów na stronie lub w zestawie stron. |
| Wystąpienie strony | Instancje strony definiują dane i zawartość wybranych stron. |

## <a name="templates"></a>Szablony

Szablony znajdują się na górze hierarchii modelu strony Dynamics 365 Commerce i stanowią ważny wczesny krok dla konfiguracji witryny. Szablony ułatwiają kontrolę spójności w rodzinie układów i stron podrzędnych przez definiowanie podstawowych struktur i opcji tworzenia układu podrzędnego i tworzenia stron. Szablony pomagają uprościć proces tworzenia treści za pomocą wstępnie zdefiniowanych, centralnie zarządzanych elementów (takich jak nagłówki i stopki) oraz przepływów tworzenia wspomaganych w celu zagwarantowania, że wybór konfiguracji modułu jest zgodny z ideą marki.

### <a name="controlling-consistency"></a>Kontrola spójności

Podczas projektowania szablonu największa decyzja biznesowa, jaką musi wykonać użytkownik, określa stopień kontroli nad procesem tworzenia strony. Szablon, który opuszcza wszystko, kto jest otwarty dla autora podrzędnego, jest najłatwiejszym typem tworzonego szablonu, ale może mieć długoterminowe konsekwencje związane z utrzymywaniem stron, które są z niego tworzone. Dobrze napisany szablon zawiera wskazówki i usprawnione doświadczenie związane z tworzeniem dokumentów, ale daje autorom wystarczającą elastyczność, dzięki czemu mogą wykonywać swoje zadania. Wszystkie te aspekty są uzależnione od poziomu kontroli ustawionej przez szablon.

Szablony mogą pomóc autorom treści w zwiększeniu wydajności i utrzymaniu marki na następujące sposoby:

- Umożliwia ograniczenie liczby modułów, które mogą być używane na stronie.
- Sugeruj domyślne ustawienia modułu i konfiguracji.
- Umożliwia jawne wybranie niektórych modułów i konfiguracji, które są kontrolowane na poziomie szablonu. Proces ten jest również nazywany *blokowaniem* ustawienia.

W poniższym przykładzie pokazano, jak można skonfigurować szablon podstawowy (szablon X):

- Wszystkie podrzędne układy szablonu X muszą mieć kontener nagłówka, kontener treści i kontener stopki.
- W szablonie X konfiguracja kontenera nagłówka jest zablokowana i może zostać zmieniona tylko w szablonie X. Wszystkie układy i strony podrzędne zawsze mają ten nagłówek.
- Kontener treści wymaga co najmniej jednego modułu i maksymalnie dziesięciu modułów. Moduły te są definiowane przez podrzędne układy i strony.
- Dla kontenera treści dostępne są moduły główne, funkcji, karuzela i baner.
- Kontener stopki jest konfigurowany w szablonie X, ale można go zastąpić podrzędnymi układami i stronami.

Szablon w tym przykładzie definiuje prostą strukturę i zbiór opcji dotyczących podrzędnych autorów zawartości. Należy zauważyć, że niektóre części strony (w tym przypadku nagłówek) są w pełni zdefiniowane i zablokowane w szablonie i nie mogą być zmieniane przez autorów podrzędnych. Inne części (w tym przypadku ciało) mogą zostać określone przez dalszych autorów w ramach określonych wytycznych (w tym przypadku minimalna liczba i maksymalna liczba modułów określonych typów). Pozostałe części (w tym przypadku stopka) są zdefiniowane w szablonie, ale mogą zostać zastąpione przez dalszych autorów.

Ważnym początkowym krokiem dla administratorów witryny i marki jest określenie właściwej równowagi między ograniczeniem a elastycznością układu potomnego i autorów stron. Gdy używane są szablony, waga jest w pełni konfigurowalna. Wpływa na to, czy elementy strony są centralnie aktualizowane (zablokowane w szablonie) czy pozostawione poszczególnym poziomom podrzędnym, które są niższe w hierarchii stron.

Aby rozpocząć korzystanie z szablonów, należy zapoznać się z [Praca z szablonami](work-with-templates.md).

## <a name="layouts"></a>Układy

Układy są kolejnym poziomem w hierarchii modelu strony, poniżej szablonów. Podczas gdy szablon definiuje wszystkie moduły, które są dozwolone dla strony, układ jest jawnym wyborem i układem modułów. Strony są kolejnym poziomem w hierarchii modelu strony, poniżej układów. Definiują one zlokalizowaną zawartość dla modułów wybranych w układzie.

Poniższy przykład bazuje na przykładzie szablonu z poprzedniej sekcji i pokazuje, jak można skonfigurować podstawowy układ:

- Szablon nadrzędny układu wymaga, aby kontener treści miał od jednego do dziesięciu modułów. Moduły te mogą być tylko modułami głównymi, funkcji, karuzeli i banerów. Dlatego układ może definiować następujący wybór i rozmieszczenie modułów:

    - Pierwszy moduł w kontenerze nadwozia jest modułem banerowym, a za nim moduł główny i dwa moduły funkcji.
    - Pierwszy moduł funkcji jest wyrównany do lewej, a drugi moduł funkcji jest wyrównany do prawej.

- Mimo że domyślna stopka jest dziedziczona z szablonu nadrzędnego, autor szablonu pozostawił stopkę odblokowaną. Dlatego układ może ją zastąpić, definiując inny fragment stopki.

Układ w tym przykładzie określa ostateczny układ modułów dla stron podrzędnych. Podobnie jak szablon, układ może definiować domyślne lub zablokowane właściwości modułu, które zawsze będą dziedziczone przez strony podrzędne (na przykład wyrównanie modułów funkcji). Rzeczywista zawartość lub dane dla każdego modułu w układzie są następnie definiowane w dalszej części hierarchii, w każdej instancji strony podrzędnej. Ważnym rozróżnieniem jest tutaj to, że układy nie zawierają bezpośrednio treści lokalizowalnej, podczas gdy ich strony podrzędne tak. Podstawową funkcją układu jest określenie ostatecznego ustawienia i domyślnej konfiguracji modułów dla jego stron podrzędnych.

Ta hierarchia jest potężna z dwóch powodów. Po pierwsze, układy, które mają ten sam szablon nadrzędny, są traktowane jako kompatybilne w scenariuszach przełączania układu. Dlatego układ dowolnej strony można zmienić na inny układ z tej samej hierarchii szablonów bez konieczności ponownego tworzenia treści na poziomie strony. Możesz skorzystać z tej możliwości, aby dokonywać sezonowych aktualizacji projektu, eksperymentować lub przeprowadzać stałe przeprojektowanie witryny. Po drugie, układy udostępniają inny sposób centralnego modyfikowania elementów współużytkowanych dla grupy stron bez konieczności aktualizowania poszczególnych stron. Na przykład, jeśli kategoria produktu ma 1000 stron o tym samym układzie, moduły można zmienić w układzie, a zmiana ta zostanie natychmiast odzwierciedlona na wszystkich 1000 stronach podrzędnych.

Dzięki zrozumieniu tej hierarchii można zapewnić adaptacyjną i wydajną strukturę witryny, która ułatwia oszczędności kosztów, jest skalowalna i daje lepsze rezultaty w miarę rozwoju witryny w czasie.

### <a name="preset-and-custom-layouts"></a>Układ predefiniowany i niestandardowy

Układy w witrynie mogą być *predefiniowane* lub *niestandardowe*:

- Ustawienie **predefiniowanych układów** umożliwia tworzenie stron przepływu pracy, w których wszystkie moduły są już wybrane i rozmieszczone, a ponadto jest wymagane wprowadzanie danych. Takie podejście może pomóc zaoszczędzić czas, gdy trzeba utworzyć wiele stron o takich samych wymaganiach dotyczących układu. Układ predefiniowany ma relację jeden-do-wielu ze swoimi stronami podrzędnymi. Dlatego jeden układ predefiniowany może służyć do centralnego sterowania układem modułów dla setek lub tysięcy stron potomnych.
- **Układy niestandardowe** są głównie układami jednorazowego osadzania się na jednej stronie. Nie są one ujawniane jako opcja podczas tworzenia innych nowych stron lub w scenariuszach zmiany układu. Zaletą tego podejścia jest to, że autor może eksperymentować, tworząc stronę z niestandardowym układem. Następnie, jeśli autor chce ponownie użyć układu dla innych stron, można go łatwo przekonwertować na układ domyślny. Nowy układ predefiniowany jest udostępniany jako opcja w przepływach pracy tworzenia stron oraz w scenariuszach przełączania układu dla stron z tej samej hierarchii szablonów. I odwrotnie, gotowe układy można rozgałęzić do układów niestandardowych. W ten sposób autor może oderwać stronę od wstępnie ustawionego układu i utworzyć nowy niestandardowy układ jednorazowego użytku. (Ten nowy układ niestandardowy jest nadal związany wszelkimi ograniczeniami w szablonie nadrzędnym).

Wstępnie ustawiony układ i niestandardowe układy są edytowane w różnych częściach zestawu narzędzi tworzenia treści. Ponieważ układy niestandardowe nie mają żadnych zależności na innych stronach, są one edytowane bezpośrednio w edytorze stron. W takim przypadku istnienie układu jest przeważnie przezroczyste dla użytkownika i jest widoczne tylko we właściwościach na poziomie strony oraz poprzez działania dla opcji układu. Ponieważ jednak zmiany w gotowych układach mogą mieć wpływ na wiele stron podrzędnych, należy je edytować w edytorze układów, w którym działania publikowania uwzględniają pełny wpływ na strony podrzędne.

Poniższe ilustracje przedstawiają scenariusze dla gotowych i niestandardowych układów.

![Wstępnie ustawione i niestandardowe scenariusze układu](../commerce/media/template-figure1.png)

Aby rozpocząć korzystanie ze wstępnie ustawionych układów, należy zapoznać się z [Praca z układami predefiniowanymi](work-with-layouts.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Praca z szablonami](work-with-templates.md)

[Praca z układami predefiniowanymi](work-with-layouts.md)

[Praca z grupami publikowania](publish-groups.md)
