---
title: Praca z fragmentami
description: W tym temacie opisano, dlaczego, kiedy i jak stosować fragmenty w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f29046ded47ed9c49a2cc841aa7c1f6492b49aec
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124366"
---
# <a name="work-with-fragments"></a>Praca z fragmentami 


[!include [banner](includes/banner.md)]

W tym temacie opisano, dlaczego, kiedy i jak stosować fragmenty w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Fragmenty umożliwiają scentralizowane tworzenie konfiguracji modułów, które muszą być ponownie używane w całym serwisie. Na przykład nagłówki, stopki i transparenty są często konfigurowane jako fragmenty, ponieważ są współużytkowane przez wiele stron. Fragmenty można traktować jako miniaturowe strony sieci Web, które można wstawiać do innych stron w witrynie. Fragmenty mają własny cykl życia. Innymi słowy, są one tworzone, przywoływane, aktualizowane i usuwane jako niezależne jednostki w narzędziach autorskich.

Po skonfigurowaniu fragmentów można ich używać wszędzie tam, gdzie moduły mogą być używane w strukturze oddziałów. Do fragmentów można odwoływać się na stronach, w układach, w szablonach i w innych fragmentach.

> [!NOTE]
> Fragmenty można zagnieżdżać do siedmiu poziomów głębokości w innych fragmentach.

Jeśli na przykład chcesz promować wydarzenie sezonowe w dużej liczbie stron w naszej witrynie, możesz użyć fragmentu. Pierwszym krokiem w procesie tworzenia nowego fragmentu jest wybranie typu modułu, od którego chcesz zacząć. W tym przykładzie można zbudować fragment z modułu głównego.

> [!NOTE]
> Fragmenty można utworzyć na podstawie dowolnego typu modułu.

Następnie można skonfigurować fragment głównego o konkretnej zawartości promocyjnej. Można je również zlokalizować w miarę potrzeb. Nowy autonomiczny fragment główny może zostać wykorzystany jako wstępnie skonfigurowany moduł w całej witrynie. Można go łatwo dodać do szablonów, do konkretnych stron lub do innych fragmentów, które mogą zawierać moduły główne.

Wszystkie miejsca, w których jest dodawany fragment, są odwołaniami do utworzonego centralnego fragmentu głównego. W przypadku publikowania zmian w fragmencie zmiany te są natychmiast odzwierciedlane we wszystkich miejscach odwołujących się do danego fragmentu w całej witrynie. Dlatego fragmenty stanowią wydajny i efektywny sposób ponownego użycia i centralnego zarządzania konfiguracjami modułów w witrynie. Efektywnie wykorzystując je, można znacząco zwiększyć dynamikę i zmniejszyć koszt związany z zarządzaniem zawartością witryny.

Na poniższej ilustracji pokazano, jak fragmenty mogą być używane do scentralizowanego tworzenia konfiguracji modułu udostępnionego w witrynie e-Commerce.

![Na ilustracji pokazano, jak fragmenty mogą być używane do scentralizowanego tworzenia konfiguracji modułu udostępnionego w witrynie e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Tworzenie fragmentu

Można utworzyć nowy fragment lub zapisać istniejącą konfigurację modułu jako fragment.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Zapisz istniejącą konfigurację modułu jako fragment

Aby przekonwertować poprzednio skonfigurowany moduł na fragment do ponownego użycia, wykonaj następujące kroki.

1. Otwórz stronę lub szablon zawierający moduł, który chcesz przekonwertować na fragment.
1. W okienku konspektu z lewej strony wybierz przycisk wielokropka (**...**) obok nazwy modułu. 
1. Wybierz **Udostępnij jako fragment**. 
1. Zostanie wyświetlone okno dialogowe. Wprowadź nazwę i metadane dla fragmentu.
1. Wybierz przycisk **OK**, aby zapisać konfigurację modułu jako fragment, który można dodać do innych stron.

Poniższy obraz przedstawia sposób zapisywania konfiguracji modułu jako fragmentu.

![Zrzut ekranu, jak zapisać konfigurację modułu jako fragment](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a>Utwórz nowy fragment.

Aby utworzyć nowy fragment, należy wykonać poniższe kroki.

1. W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.
1. Wybierz **Nowy fragment strony**. Zostanie wyświetlone okno dialogowe, w którym są wyświetlane wszystkie dostępne typy modułów. Jak wspomniano wcześniej, fragmenty można tworzyć z poziomu dowolnego typu modułu.
1. Wybierz typ modułu dla danego fragmentu.

Poniższy rysunek przedstawia miejsce utworzenia nowego fragmentu.

![Zrzut ekranu, gdzie należy utworzyć nowy fragment](./media/fragment-nav-menu.png)

> [!TIP]
> Wybór typu ogólnego modułu kontenera zapewnia największą elastyczność, jeśli należy później zaktualizować i skonfigurować fragment.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Dodawanie, usuwanie i edytowanie fragmentów na stronie

W poniższych procedurach opisano sposób dodawania, usuwania i edytowania fragmentów.

### <a name="add-a-fragment"></a>Dodaj fragment

Aby dodać fragment do strony, wykonaj następujące kroki.

1. W okienku konspektu z lewej strony wybierz kontener lub gniazdo, do którego można dodać moduły podrzędne.
1. Wybierz przycisk wielokropka obok nazwy kontenera lub gniazda, a następnie wybierz opcję **Dodaj fragment**. Zostanie wyświetlone okno dialogowe.

    ![Zrzut ekranu, jak dodać istniejący fragment do gniazda lub kontenera](./media/add-fragment.png)
 
    > [!NOTE]
    > Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj fragment** jest niedostępna
    
1. W oknie dialogowym wyszukaj i wybierz fragment do dodania. Jeśli na liście nie ma dostępnych fragmentów, może być konieczne utworzenie fragmentu z typu modułu, który jest obsługiwany przez wybrany kontener lub gniazdo.
1. Wybierz wybrany fragment do dodania go do kontenera lub gniazda na stronie.

    ![Zrzut ekranu okna modalnego selektora fragmentów](./media/fragment-picker.png)

> [!NOTE]
> Moduły dozwolone w kontenerze lub gnieździe są definiowane przez szablon strony lub definicje modułów.

### <a name="remove-a-fragment"></a>Usuwanie fragmentu

Aby usunąć fragment z gniazda lub kontenera na stronie, wykonaj następujące kroki.

1. W okienku konspektu z lewej strony wybierz przycisk wielokropka obok nazwy fragmentu do usunięcia, a następnie wybierz ikonkę kosza na śmieci.
1. Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia fragmentu wybierz przycisk **OK**.

> [!NOTE]
> Usunięcie fragmentu ze strony powoduje jedynie usunięcie odwołania do niego z tej strony. **Nie** można usunąć tego fragmentu z witryny. Aby usunąć fragmenty z witryny, należy skorzystać z interfejsu użytkownika inspektora fragmentów (UI). Fragmenty można usuwać z witryny tylko w przypadku, gdy nie odwołują się do nich żadne strony, szablony i inne fragmenty.

### <a name="edit-a-fragment"></a>Edytuj fragment

Aby edytować fragmenty, należy skorzystać z interfejsu użytkownika edytora fragmentów. Jest to celowe ograniczenie. Pomaga zagwarantować, że autorzy nie będą mylić procesu edycji modułów dla konkretnej strony z procesem edycji fragmentów, które mogą być współużytkowane przez wiele stron.

Aby edytować fragment, należy wykonać poniższe kroki.

1. W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.
1. W obszarze **Fragmenty** wybierz fragment do edycji.
1. Edytuj właściwości i strukturę modułu fragmentu stosownie do potrzeb. Proces ten przypomina proces edycji modułów, który jest edytowany w widoku edytora stron.

Fragment można również edytować, zaznaczając go na stronie, w szablonie lub w fragmencie nadrzędnym, a następnie wybierając opcję **Edytuj fragment** w okienku właściwości po prawej stronie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Praca z szablonami](work-with-templates.md)

[Praca z układami predefiniowanymi](work-with-layouts.md)

[Praca z grupami publikowania](publish-groups.md)
