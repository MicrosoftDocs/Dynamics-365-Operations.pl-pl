---
title: "Wyświetlanie i eksportowanie opisów pól"
description: "W tym artykule opisano, jak wyświetlać opisy pól i jak używać strony Opisy pól do eksportowania opisów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 7898ff427ede4447a5798d4989ffd3088a776d9c
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Wyświetlanie i eksportowanie opisów pól
<a id="view-and-export-field-descriptions" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak wyświetlać opisy pól i jak używać strony Opisy pól do eksportowania opisów.

Program Microsoft Dynamics 365 for Finance and Operations zawiera opisy niektórych bardziej skomplikowanych pól. Opisy te są wyświetlane po umieszczeniu wskaźnika myszy na danym polu. Strona **Opisy pól** umożliwia także przeglądanie i eksportowanie opisów. 

Nie wszystkie strony mają opisy pól. Chcemy podać opisy jedynie dla bardziej złożonych pól, a nie tych, których funkcja jest oczywista. Dlatego niektóre strony nie mają żadnych opisów pól, niektóre mają kilka opisów, za to te bardziej złożone strony, np. wiele stron parametrów, zawierają wiele opisów. 

Jeśli masz dostęp do środowiska programistycznego programu Finance and Operations, istnieje możliwość dodawania nowych opisów pól i modyfikowania istniejących opisów. Na przykład do opisu pola można dodać informacje specyficzne dla firmy. Aby uzyskać więcej informacji, zobacz [Dostosowywanie pomocy pól](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help).

## Wyświetlanie opisów pól w interfejsie użytkownika
<a id="see-field-descriptions-in-the-user-interface" class="xliff"></a>
Opisy pól można wyświetlić, umieszczając kursor myszy nad polem. Jeśli opis nie jest dostępny, po umieszczeniu wskaźnika myszy na polu zobaczysz nazwę pola. (Uwaga: w wersji Dynamics AX 7.0 (z lutego 2016 r.) opisy pól można wyświetlać tylko na stronie **Opisy pól**). Na poniższej ilustracji przedstawiono opis pola, który pojawia się po umieszczeniu wskaźnika myszy nad polem **Zablokuj pozycje podczas inwentaryzacji**. 

[![Przykład opisu pola](./media/field-description.png)](./media/field-description.png)

## Używanie strony Opisy pól do wyświetlania i eksportowania pomocy dla pól
<a id="use-the-field-descriptions-page-to-view-and-export-field-help" class="xliff"></a>
Strona **Opisy pól** umożliwia przeglądanie i eksportowanie opisów pól. Dostępne opisy można wyświetlić opisy dla jednej strony naraz.

### Zobacz opisy dla strony
<a id="view-the-descriptions-for-a-page" class="xliff"></a>

Aby wyświetlić opisy dla strony, wykonaj następującą czynność:

-   W polu **Wybór strony** wpisz nazwę strony. Alternatywnie kliknij strzałkę, aby otworzyć listę wszystkich stron, a następnie przejrzyj lub wyfiltruj listę.

Można użyć nazwy strony wyświetlanej w interfejsie użytkownika (na przykład **Odbiorcy**) lub nazwy kodowej (nazwy w drzewie obiektów aplikacji) dostępnej po kliknięciu strony prawym przyciskiem myszy (na przykład **CustTable**). 

Aby uzyskać informacje o różnych sposobach filtrowania listy stron, zobacz sekcję „Wyszukiwanie strony” w dalszej części tego artykułu. 

Jeśli w opcji **Uwzględnij pola bez opisu** zaznaczysz wartość **Tak**, będą wyświetlane wszystkie pola istniejące na stronie, nawet jeśli nie mają opisów pól.

### Eksportuj opisy dla strony
<a id="export-the-descriptions-for-a-page" class="xliff"></a>

Aby wyeksportować opisy dla strony, wykonaj następujące czynności:

1.  W polu **Wybór strony** zaznacz stronę.
2.  W prawym górnym rogu kliknij przycisk **Otwórz w Microsoft Office**, a następnie wybierz opcję **FieldDescriptionTmp**.

### Wyszukiwanie strony
<a id="searching-for-a-page" class="xliff"></a>

Istnieje kilka sposobów, aby wyszukać stronę w polu **Wybór strony**. W wielu przypadkach trzeba kliknąć strzałkę w polu pola **Wybór strony**, aby otworzyć listę rozwijaną, a następnie wybrać stronę z wyfiltrowanej listy.

-   Wpisz część nazwy, a następnie otwórz listę rozwijaną i wybierz stronę w wyfiltrowanej listy.
-   Otwórz listę rozwijaną, a następnie kliknij nagłówek **Nazwa strony** u góry listy lub nagłówek **Nazwa drzewa obiektów aplikacji (AOT) strony**. Zostanie otwarte okno dialogowe, w którym można użyć zaawansowanych opcji filtrowania, np. **Nazwa strony zaczyna się od**.
-   Wpisz pełną nazwę strony. Po wybraniu tej opcji najlepiej otworzyć listę rozwijaną i sprawdzić, co jeszcze jest na niej, nawet gdy są wyświetlane opisy pól.
    -   W przypadku istnienia jednego dokładnego dopasowania do nazwy zostaną wyświetlone opisy pól dla tej strony.
    -   Jeśli istnieje więcej niż jedno dokładne dopasowanie, opisy nie są wyświetlane. Należy otworzyć listę rozwijaną i wybrać żądaną stronę.
    -   Jeśli wpisywana nazwa jest częścią nazwy innej strony, zobaczysz opisy dla swojej strony. Jednak po otwarciu listy rozwijanej zobaczysz dodatkowe strony, których tytuły zawierają w sobie tę nazwę.

Na przykład nie są wyświetlane żadne opisy po wpisaniu **Inwentaryzacja** w polu ****Wybór strony****. Otwierasz listę rozwijaną i widzisz, że istnieją dwie strony o nazwie **Inwentaryzacja**, a także kilka stron, w których wyraz „Inwentaryzacja” jest częścią nazwy. Jeśli wybierzesz stronę o nazwie **InventJournalCount** w drzewie obiektów aplikacji, opisy pól są wyświetlane dla tej strony. Jednakże jeśli lista rozwijana zostanie otwarta ponownie, będzie zawierać wszystkie strony, które w nazwie strony w drzewie obiektów aplikacji mają tekst „InventJournalCount”.

## Rozwiązywanie problemów
<a id="troubleshooting" class="xliff"></a>
Ta sekcja zawiera informacje pomocne w rozwiązywaniu problemów, które mogą wystąpić podczas używania opisów pól.

### Nie można odnaleźć opisu pola
<a id="i-cant-find-a-field-description" class="xliff"></a>

Pracujemy nad dodaniem opisów bardziej skomplikowanych pól. Jeśli potrzebujesz pomocy dla określonego pola, daj nam znać przez dodanie komentarza do tego tematu.

### Opis pola nie jest pomocny.
<a id="the-field-description-isnt-helpful" class="xliff"></a>

Daj nam znać przez dodanie komentarza do tego tematu. Jeśli to możliwe, opisz dodatkowe informacje, których potrzebujesz.

### Nie mogę znaleźć pola na stronie Opisy pól
<a id="i-cant-find-a-field-on-the-field-descriptions-page" class="xliff"></a>

Aby wyświetlić wszystkie pola na stronie, ustaw opcję **Uwzględnij pola bez opisu** na **Tak**. Kliknij pole **Wybór strony**, aby sprawdzić, czy została wybrana poprawna strona. Jeśli wpisana nazwa jest częścią nazwy innego pola, być może wybrano stronę, która ma dłuższą nazwę.

### Nie mogę znaleźć strony na stronie Opisy pól
<a id="i-cant-find-a-page-on-the-field-descriptions-page" class="xliff"></a>

Aby uzyskać informacje o różnych sposobach znajdowania stron, zobacz sekcję „Wyszukiwanie stron” wcześniej w tym artykule. Jeśli została wpisana dokładna nazwa strony, opisy pól mogą nie być pokazywane, gdy więcej niż jedna strona ma tę samą nazwę. Kliknij strzałkę w polu **Wybór strony**, aby otworzyć wyfiltrowaną listę dostępnych stron.

Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Dostosowywanie pomocy pól](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help)





