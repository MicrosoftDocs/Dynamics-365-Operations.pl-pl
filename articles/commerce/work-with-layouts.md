---
title: Praca z układami predefiniowanymi
description: W tym temacie opisano, jak pracować z układami predefiniowanymi w Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 57dc0de64ce7536cf70c1f277d5212c3b8dd7480
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009600"
---
# <a name="work-with-preset-layouts"></a>Praca z układami predefiniowanymi


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak pracować z układami predefiniowanymi w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Przed wykonaniem procedur opisanych w tym temacie należy koniecznie przeczytać [Układ predefiniowany i niestandardowy](templates-layouts-overview.md#preset-and-custom-layouts). Aby zapoznać się z ogólnym omówieniem, zajrzyj do [Omówienie szablonów i układów](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Tworzenie nowego układu predefiniowanego

Są dwie metody tworzenia predefiniowanego układu. Istniejący układ niestandardowy można zapisać jako nowy układ predefiniowany lub można utworzyć predefiniowany układ od podstaw.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Tworzenie predefiniowanego układu na podstawie istniejącego układu niestandardowego

Aby utworzyć układ predefiniowany z istniejącego układu niestandardowego, wykonaj następujące kroki.

1. Umożliwia otwarcie istniejącej strony, w której obecnie nie jest używany układ predefiniowany, a także strukturę modułu, której użytkownik chce użyć do ponownego użycia w odniesieniu do innych stron w witrynie.
1. Wybierz **Edytuj**, aby wyewidencjonować stronę.
1. Wybierz **Zapisz jako nowy układ**. Zostanie wyświetlone okno dialogowe **Zapisz jako nowy układ**.
1. Wprowadź nazwę i opis predefiniowanego układu. Wprowadzone wartości będą widoczne dla innych autorów, tworząc nowe strony z układu lub przełączając do niego. Dlatego należy wprowadzić wartości, które będą przydatne autorom stron.
1. Kliknij przycisk **OK**.

Układ predefiniowany będzie teraz dostępny w przypadku tworzenia nowych stron lub wybrania innego układu strony w tej samej hierarchii szablonów.

> [!TIP]
> Aby szybko sprawdzić, czy konkretna strona jest aktualnie powiązana z ustawionym układem, wybierz stronę w widoku listy stron i sprawdź metadane układu w panelu właściwości po prawej stronie.

### <a name="create-a-new-preset-layout"></a>Tworzenie nowego układu predefiniowanego

Aby utworzyć układ predefiniowany od zera, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie zaznacz **Układy**.
1. Wybierz **Nowy układ**. Zostanie wyświetlone okno dialogowe **Nowy układ**.
1. Wybierz szablon, który ma być używany w układzie predefiniowanym.
1. Wprowadź nazwę i opis predefiniowanego układu. Wprowadzone wartości będą widoczne dla innych autorów, tworząc nowe strony z układu lub przełączając do niego. Dlatego należy wprowadzić wartości, które będą przydatne autorom stron.
1. Wybierz przycisk **OK**, aby utworzyć nowy układ predefiniowany i otworzyć edytor układu.
1. W edytorze układu dodaj i skonfiguruj moduły, korzystając z drzewa konspektu po lewej stronie i okienka właściwości po prawej stronie. (Proces ten przypomina proces dodawania i konfigurowania modułów szablonu w edytorze szablonów.) Układ modułów i wszelkie zablokowane ustawienia domyślne stają się scentralizowaną konfiguracją modułu dla stron używających tego układu predefiniowanego.

## <a name="modify-a-preset-layout"></a>Modyfikowanie predefiniowanego układu

Aby modyfikować układ predefiniowany, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie zaznacz **Układy**.
1. W edytorze układu, w drzewie konspektu z lewej strony, wybierz moduł do zmodyfikowania. Następnie wykonaj jeden z następujących kroków:

    - Aby przenieść moduł w górę lub w dół wewnątrz jego elementu nadrzędnego, wybierz przycisk wielokropeka (**...**) dla modułu, a następnie wybierz opcję **Przenieś w górę** lub **Przenieś w dół**.
    - Aby zmienić domyślne ustawienia modułu, należy w okienku właściwości wprowadzić wartości domyślne i opcjonalnie je zablokować dla wszystkich podrzędnych stron.
    - Aby dodać nowe moduły lub fragmenty do modułów kontenerów, wybierz przycisk wielokropeka, a następnie wybierz opcję **Dodaj moduł** lub **Dodaj fragment**.
    - Aby usunąć moduł z układu, wybierz przycisk wielokropek, a następnie wybierz opcję **Usuń**.

## <a name="change-a-preset-layout-theme"></a>Zmienianie wstępnie ustawionego motywu układu

Typową praktyką jest ustawienie domyślnego motywu dla wszystkich stron używających predefiniowanego układu.

Aby ustawić lub zmienić motyw dla wszystkich stron podrzędnych korzystających z układu predefiniowanego, wykonaj następujące kroki.

1. W edytorze układu, w drzewie konspektu z lewej strony, wybierz moduł kontenera strony. (Zazwyczaj ten moduł jest drugim węzłem i ma nazwę **Strona domyślna**.)
1. W okienku właściwości po prawej stronie w polu **motyw** wybierz motyw.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Zapisywanie, zaewidencjonuj, przejrzyj i opublikuj predefiniowany układ

Aby zapisać i zewidencjonować predefiniowany układ, wykonaj następujące kroki.

1. Wybierz opcję **Zapisz** u góry edytora układu. Zapisane zmiany nie wpływają na strony podrzędne, dopóki nie zostaną zaewidencjonowane.
1. Wybierz opcję **Zakończ edycję**. Twoje zmiany są teraz wykrywalne dla podrzędnych przepływów pracy.

Aby wyświetlić podgląd zmian, należy otworzyć istniejącą stronę, która używa tego predefiniowanego układu, lub utworzyć nową stronę na podstawie tego układu.

Po przejrzeniu zmian w predefiniowanym szablonie należy wykonać jedną z następujących czynności, aby opublikować układ w witrynie na żywo:

* Przejdź do **Układy**, wybierz układ, a następnie wybierz opcję **Opublikuj**.
* Wybierz nazwę układu, aby otworzyć edutor ukałdu, a następnie wybierz **Publikuj**.
* Umożliwia opublikowanie strony, która odwołuje się do nieopublikowanego układu. Układ zostanie automatycznie opublikowany.

> [!WARNING]
> Do dostępnych układów mogą odwoływać się wiele stron. Publikując predefiniowany układ, należy pamiętać, że może on mieć wpływ na układ wielu stron.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Praca z szablonami](work-with-templates.md)
