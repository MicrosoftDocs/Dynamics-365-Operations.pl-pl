---
title: Praca z szablonami
description: W tym artykule opisano, jak pracować z szablonami w Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: cbe9d103da9c86dcf3aad54ec036282d2bb3faca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282688"
---
# <a name="work-with-templates"></a>Praca z szablonami

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak pracować z szablonami w Microsoft Dynamics 365 Commerce.

Zgodnie z tematem [Omówienie szablonów i układów](templates-layouts-overview.md), szablony definiują zbiór opcji dostępnych dla autorów podrzędnych. Szablony są przydatne dla zespołu tworzenia sieci Web w przedsiębiorstwie z kilku powodów, a strukturalne dobre szablony mogą pomóc we wszystkich następujących celach:

- Uprość tworzenie treści dzięki codziennym rolom edytora treści.

    - Filtrowanie opcji modułu, tak aby były pokazywane tylko odpowiednie moduły dla konkretnej sekcji strony. (Na przykład sekcja marketingowa szablonu może być skonfigurowana do odfiltrowywania nieistotnych modułów, których nigdy nie należy używać w tym kontekście, a to tylko skomplikuje zadania tworzenia treści, jeśli zostaną wyświetlone).
    - Skonfiguruj domyślne ustawienie modułu, aby zwiększyć efektywność tworzenia.
    - Definiowanie domyślnych fragmentów stron w celu zwiększenia wydajności tworzenia. (Na przykład fragmenty nagłówka i stopki w szablonie będą automatycznie wyświetlane na każdej stronie podrzędnej.)

- Umożliwia zachowanie marki dla witryn w przedsiębiorstwie przez zdefiniowanie zatwierdzonego zbioru rozmieszczenia modułów oraz opcji konfiguracji.

    > [!TIP] 
    > Pomyślne witryny e-Commerce umożliwiają klientom korzystanie z znanych, powtarzalnych i nieoznakowanych wzorców projektowania użytkowników (UX). Użycie szablonów ułatwia kontrolowanie spójności w witrynie.

- Wyniki optymalizacji aparatu wyszukiwania (SEO) można ulepszyć przez zapewnienie powtarzalnych i programowo zdefiniowanych definicji stron i metadanych.

> [!NOTE]
> Chociaż szablony są zaprojektowane pod kątem kontroli spójności w witrynie, można je teoretycznie konfigurować, aby nie wymuszać spójności. Marki i administratorzy witryn mogą definiować dowolny poziom zmienności stron w ich oddziale. Na przykład szablon może pozostać całkowicie otwarty, dzięki czemu autorzy zawartości mogą utworzyć dowolny projekt strony. W takim przypadku nie są dostępne żadne świadczenia z poprzedniej listy.

## <a name="modify-a-template"></a>Modyfikowanie szablonu

Szablony są modyfikowane za pomocą edytora szablonów.

Aby otworzyć edytor szablonów w kreatorze witryn Commerce, wykonaj jeden z poniższych kroków:

- W okienku nawigacji w witrynie wybierz pozycję **Szablony**, a następnie wybierz szablon do zmodyfikowania.
- W edytorze stron dla istniejącej strony wybierz węzeł górny w drzewie konspektu z lewej strony. Następnie w okienku właściwości po prawej stronie wybierz opcję **Edytuj szablon**.

Widok drzewa konspektu po lewej stronie zawiera opcje i struktury modułu dostępne dla podrzędnych układów i stron. Po wybraniu modułu w drzewie konspektu można wyświetlić właściwości szablonu dla wybranego modułu w okienku właściwości po prawej stronie. Niektóre z tych właściwości są unikatowe dla edycji szablonów. W poniższej tabeli opisano te właściwości.

| Nazwa właściwości | Opis |
|---|---|
| Minimalna liczba wystąpień | Ta właściwość określa minimalną liczbę wystąpień wybranego modułu. Jeśli na przykład wartość jest ustawiona na **1**, moduł jest wymagany dla autorów podrzędnych, natomiast jeśli wartość jest ustawiona na **0** (zero), moduł jest opcjonalny. |
| Maksymalna liczba wystąpień | Ta właściwość określa maksymalną liczbę wystąpień wybranego modułu. Jeśli na przykład wartość jest ustawiona na **1**, moduł można dodać tylko jeden raz. |
| Min. moduły (Kontenery) | W przypadku modułów, które zawierają inne moduły (czyli dla *modułów kontenerów*), ta właściwość definiuje minimalną liczbę modułów, które powinny zostać dodane jako elementy podrzędne. Na przykład dla modułu karuzeli wartość może być ustawiona na liczbę większą niż 1. |
| Max. moduły (Kontenery) | W przypadku modułów kontenera ta właściwość definiuje maksymalną liczbę modułów, które powinny zostać dodane jako elementy podrzędne. Na przykład dla modułu karuzeli wartość może być ustawiona na liczbę mniejszą niż 10. |
| Zablokowano | Obok wszystkich właściwości modułu podstawowego zostanie wyświetlona **zablokowana** kontrola logiczna. Pozwala to autorowi szablonów na zablokowanie ustawienia modułu w szablonie. Zablokowane ustawienie modułu nie może być zastąpione przez żadną inną podrzędną układu lub strony. Staje się centralnie edytowalną wartością właściwości dla wszystkich układów i stron korzystających z szablonu. |

## <a name="create-a-new-template"></a>Utwórz nowy szablon

Aby utworzyć szablon w konstruktorze witryn, należy wykonać następujące kroki.

1. W okienku nawigacji w witrynie wybierz pozycję **Szablony**, a następnie otwórz szablon w widoku inspekcji.
1. Wybierz **Nowy szablon**.
1. W oknie dialogowym tworzenia szablonu wprowadź nazwę i opis szablonu. Wprowadzone wartości będą widoczne dla autorów podczas tworzenia nowych stron. Dlatego należy wprowadzić metadane, które będą przydatne autorom stron. Na przykład wprowadź **Ten szablon służy do tworzenia ogólnych stron marketingowych** jako opis. Te metadane można później edytować.
1. Wybierz przycisk **OK**, aby utworzyć nowy szablon i otworzyć edytor szablonów. Edytor szablonów pokazuje drzewo konspektu po lewej stronie i okienko właściwości po prawej stronie.
1. W drzewie konspektu rozwiń węzły i wybierz gniazdo **nagłówka HTML**.
1. Jeśli w tym gnieździe nie ma jeszcze żadnych modułów, należy wybrać przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz **Podsumowanie domyslnej strony** i wybierz przycisk **OK**.
1. W drzewie konspektu wybierz nowy moduł, a następnie w okienku właściwości wprowadź wszystkie ustawienia domyślne, które powinny być konfigurowane automatycznie dla wszystkich stron podrzędnych szablonu. Jeśli nie chcesz dodawaj żadnych ustawień domyślnych, pozostaw te wartości puste.
1. W drzewie konspektu wybierz **Treść**, następnie wybierz przycisk wielokropka, a następnie wybierz pozycję **Dodaj moduł**.
1. Wybierz moduł kontenera strony (może być tylko jedna opcja), a następnie kliknij przycisk **OK**.

W obszarze nowy kontener strony zostanie wyświetlony nowy zbiór gniazd (**nagłówek**, **główne** itd.). W tym miejscu można dodać i skonfigurować opcje modułu, które będą dostępne dla autorów podczas tworzenia stron z tego szablonu. Domyślnie, jeśli żadne moduły nie są dodawane do gniazda, obsługiwane są wszystkie dostępne typy modułów dla tego gniazda.

Szablon jest teraz technicznie prawidłowy i może być zapisany, zaewidencjonowany i używany do tworzenia nowych stron. Jednak następne trzy sekcje opisują niektóre inne ustawienia domyślne, które można skonfigurować jako pierwsze.

## <a name="add-a-header-and-a-footer"></a>Dodawanie nagłówka i stopki

Jeśli twoja witryna posiada już fragment nagłówka, wykonaj poniższe kroki w konstruktorze witryn, aby dodać nagłówek i stopkę do szablonu.

1. W drzewie konspektu rozwiń miejsce w **treści** i podrzędny moduł strony.
1. Wybierz gniazdo **nagłówka**.
1. Wybierz przycisk wielokropka (...) dla gniazda **Nagłówek**, a następnie wybierz opcję **Dodaj fragment**.
1. Wyszukaj i wybierz fragment nagłówka oddziału, a następnie kliknij przycisk **OK**.

Wszystkie strony korzystające z szablonu będą teraz automatycznie dziedziczyły ten fragment nagłówka.

Jeśli witryna nie ma jeszcze fragmentu nagłówka, zapoznaj się z tematem [Tworzenie fragmentu](work-with-fragments.md#create-a-fragment), aby uzyskać informacje na temat sposobu jego utworzenia, a następnie wykonaj poprzednią procedurę.

## <a name="change-the-template-theme"></a>Zmień szablon motywu

Aby określić domyślny motyw dla wszystkich stron korzystających z szablonu, wykonaj następujące kroki w konstruktorze witryn.

1. W drzewie konspektu z lewej strony rozwiń gniazdo w **treści**.
1. W gnieździe **treści** wybierz moduł kontenera strony (na przykład **strona domyślna**).
1. W okienku właściwości po prawej stronie w polu **motyw** wybierz motyw.

Domyślnie wszystkie nowe strony używają teraz wybranej kompozycji. Aby strony nie miały zastąpienia tego ustawienia na poziomie układu lub strony, należy ustawić dla **zablokowanej** kontrolki logicznej wartość **prawda**.

## <a name="add-a-script-to-a-template"></a>Dodawanie skryptu do szablonu

Do szablonu można dodawać elementy **&lt;skryptu&gt;** HTML zawierające kod JavaScript. W ten sposób można udostępnić domyślne zachowania skryptów w sekcjach nagłówka HTML, początku treści oraz końcowych treści stron.

Aby dodać skrypt do szablonu w konstruktorze stron, należy wykonać następujące kroki.

1. W drzewie konspektu z lewej strony wybierz gniazdo, w którym chcesz dodać element **&lt;skryptu&gt;** (np. nagłówek HTML, początek treści lub zakończenie treści).
1. Wybierz przycisk wielokropka (...) dla gniazda, a następnie wybierz opcję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł skryptu ( np. **skrypt zewnętrzny** lub **skrypt wbudowany**).
1. W okienku właściwości po prawej stronie, w odpowiednim formancie właściwości skryptu (np. **skrypt wbudowany** lub **tagi skryptu**) wprowadź odpowiedni skrypt.
1. W okienku właściwości wprowadź inne ustawienia opcjonalne, które chcesz skonfigurować.

> [!TIP]
> Jeśli chcesz ponownie użyć dowolnego z modułów skryptów dla innych szablonów, możesz przekonwertować je na fragmenty. W ten sposób użytkownik pomaga zwiększyć efektywność procesu tworzenia i scentralizowa proces aktualizacji. Aby uzyskać informacje na temat konwertowania modułu skryptu na fragment, zapoznaj się z tematem [Zapisz istniejącą konfigurację modułu jako fragment](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Zapisywanie, zaewidencjonuj, przejrzyj i opublikuj szablon

Aby zapisać i zewidencjonować szablon w konstruktorze witryn, wykonaj następujące kroki.

1. Wybierz opcję **Zapisz** u góry edytora szablonów. Zapisane zmiany nie wpływają na strony podrzędne, dopóki nie zostaną zaewidencjonowane.
1. Wybierz opcję **Zakończ edycję**. Twoje zmiany są teraz wykrywalne dla podrzędnych przepływów pracy.

Aby wyświetlić podgląd zmian, należy otworzyć istniejącą stronę, która używa tego szablonu, lub utworzyć nową stronę na podstawie tego szablonu.

Po przejrzeniu zmian w szablonie należy wykonać jedną z następujących czynności, aby opublikować szablon w witrynie na żywo:

* Przejdź do **Szablony**, wybierz szablon, a następnie wybierz opcję **Opublikuj**.
* Wybierz nazwę układu, aby otworzyć edutor ukałdu, a następnie wybierz **Publikuj**.
* Umożliwia opublikowanie strony, która odwołuje się do nieopublikowanego szablonu. Szablon zostanie automatycznie opublikowany.

> [!WARNING]
> Po opublikowaniu szablon lub dowolny inny element systemu zarządzania zawartością (CMS) jest wykrywalny w Internecie. Nie Publikuj dokumentów ani zasobów, dopóki nie przygotujesz ich do publicznego udostępnienia. Wersje dokumentów, które zostały zapisane i zaewidencjonowane, ale nie zostały opublikowane, są wykrywalne tylko dla uwierzytelnionych użytkowników systemu.

## <a name="rename-a-template"></a>Zmiana nazwy szablonu

Aby zmienić nazwę istniejącego szablonu w kreatorze witryn, wykonaj poniższe kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Szablony**.
1. Wybierz nazwę szablonu, którego nazwę chcesz zmienić.
1. Wybierz pozycję **Edytuj**, aby rozpocząć edytowanie szablonu. Zauważ, że nie możesz edytować szablonu, jeśli ktoś inny już go edytuje.
1. W okienku właściwości szablonu wybierz symbol pióra znajdujący się obok nazwy.
1. Edytuj nazwę szablonu stosownie do potrzeb.
1. Zaznacz znacznik wyboru, aby potwierdzić zmianę nazwy.
1. Wybierz opcję **Zakończ edycję**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Praca z układami predefiniowanymi](work-with-layouts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
