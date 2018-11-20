---
title: "Funkcje związane z ułatwianiem dostępu"
description: "W tym temacie opisano funkcje, które pomagają użytkownikom z różnymi niepełnosprawnościami korzystać z rozwiązań Dynamics 365 for Finance and Operations, Dynamics 365 for Retail i Dynamics 365 for Talent."
author: TLeforMicrosoft
manager: AnnBe
ms.date: 11/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a67b51ced4bea11be258aed359a758d88294beb1
ms.openlocfilehash: bc48aa5ccf50705ef0c5087608798875953fe888
ms.contentlocale: pl-pl
ms.lasthandoff: 11/05/2018

---

# <a name="accessibility-features"></a>Funkcje ułatwień dostępu

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które pomagają użytkownikom z różnymi niepełnosprawnościami korzystać z rozwiązań Dynamics 365 for Finance and Operations, Dynamics 365 for Retail i Dynamics 365 for Talent. Dostępne są na przykład funkcje przeznaczone dla osób korzystających z technologii wspomagających dla osób z wadami wzroku, takich jak Narrator w systemie Microsoft Windows.

## <a name="windows-narrator-and-keyboard-only-access"></a>Narrator w systemie Windows i dostęp wyłącznie za pomocą klawiatury

Każde pole i każdy element sterowania ma etykietę oraz opis dostępnych skrótów. Czytnik ekranu może odczytać etykietę oraz opis.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Skróty do najczęściej wykonywanych akcji

W przypadku większości użytkowników codzienna praca z systemem wiąże się z dużą ilością wprowadzania danych oraz interakcji z klawiaturą. W celu zwiększenia wygody użytkownika utworzono skróty, które pomogą „skakać” po ekranie oraz skróty umożliwiające wykonywanie akcji specjalnych. Aby uzyskać więcej informacji, zobacz temat [Skróty klawiszowe](shortcut-keys.md)

## <a name="navigation-search"></a>Nawigacja z wyszukiwaniem

Każda strona dostępna za pomocą menu okienka nawigacji z lewej strony jest również dostępna z poziomu pola **Wyszukaj**. Za pomocą skrótu Alt + G uaktywnij pole **Wyszukaj**, a następnie wpisz nazwę lub opis strony.

![Hasło „konta bankowe” wprowadzone w polu wyszukiwania](media/6d08b0be32808221023e2aa92d69fd70.png  "Hasło „konta bankowe” wprowadzone w polu wyszukiwania")

Aby uzyskać więcej informacji, zobacz [Nawigacja z wyszukiwaniem](navigation-search.md).

> [!NOTE]
> Można przejść bezpośrednio do tylko strony najwyższego poziomu. Strony podrzędne opierają się na informacjach lub kontekście ze strony nadrzędnej.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Wyszukiwanie akcji dla użytkowników samej klawiatury lub przy wprowadzaniu danych z papierowej dokumentacji znajdującej się na biurku

Z każdej akcji dostępnej na stronie można skorzystać za pomocą klawiatury, poprzez sekwencję tabulacji. Informacje na temat sekwencji tabulacji znajdują się w dalszej części tego tematu. Aby uruchamiać akcje w sposób bardziej bezpośredni, można użyć funkcji wyszukiwania akcji.

### <a name="example"></a>Przykład

Chcesz uruchomić akcję **Dziennik powiadomień pocztą E-mail**, która znajduje się w grupie **Powiadomienie pocztą E-mail** na karcie **Zamówienie sprzedaży** w okienku akcji.

![Akcja Dziennik powiadomień pocztą E-mail w okienku akcji](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg  "Akcja Dziennik powiadomień pocztą E-mail w okienku akcji")

Jedną z opcji jest użycie klawiatury. Naciśnij kombinację klawiszy Ctrl + F6, aby uaktywnić okienko akcji, a następnie naciskaj klawisz Tab, aby przechodzić kolejno między kartami i akcjami do momentu uaktywnienia akcji **Dziennik powiadomień pocztą E-mail**.

Jednak można również uruchomić akcję bardziej bezpośrednio. Z dowolnego miejsca na stronie naciśnij kombinację klawiszy Ctrl + apostrof ('), aby wyświetlić pole wyszukiwania akcji.

![Pole wyszukiwania akcji](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg  "Pole wyszukiwania akcji")

W polu wyszukiwania wpisz wyrazy opisujące akcji. Akcja zostanie udostępniona i będzie ją można uruchomić bezpośrednio. Na przykład po wpisaniu **e-mail**, **powiadom** (część wyrazu) lub **dziennik** można „przeskoczyć” do funkcji Dziennik powiadomień pocztą E-mail.

![Hasło „e-mail” wprowadzone w polu wyszukiwania](media/image4.png "Hasło „e-mail” wprowadzone w polu wyszukiwania") 

![Hasło „powiadom” wprowadzone w polu wyszukiwania](media/image5.png "Hasło „powiadom” wprowadzone w polu wyszukiwania")

![Hasło „dziennik” wprowadzone w polu wyszukiwania](media/image6.png "Hasło „dziennik” wprowadzone w polu wyszukiwania")

Po zakończeniu można ponownie nacisnąć kombinację klawiszy Ctrl + apostrof, aby powrócić do pola, które było aktywne, zanim uruchomiono wyszukiwanie akcji.

Aby uzyskać więcej informacji, zobacz [Wyszukiwanie akcji](action-search.md).

## <a name="tab-sequence"></a>Sekwencja przejść za pomocą klawisza Tab

W trakcie codziennego korzystania z systemu nie każde pole jest wymagane do wykonania typowych zadań. Dlatego domyślnie sekwencja przejść za pomocą klawisza Tab jest „zoptymalizowana”. Naciśnięcia klawisza Tab powodują przejścia wyłącznie do pól kluczowych w typowych scenariuszach.

Może się jednak okazać, że niektóre pola używane często przez użytkownika podczas wykonywania zadań nie zostały uwzględnione w domyślnej sekwencji przejść za pomocą klawisza Tab. Jeśli w takim przypadku użytkownik korzysta z Narratora w systemie Windows, można użyć akcji klawiszowych tego Narratora w celu przejścia do takich pól i sprawdzenia ich zawartości. Alternatywnie można użyć opcji **Rozszerzona sekwencja użycia klawisza Tab** dostępnej na stronie **Opcje**. Ta opcja spowoduje umieszczenie wszystkich pól edytowalnych i tylko do odczytu w sekwencji przejść za pomocą klawisza Tab. Następnie, korzystając z funkcji personalizacji strony, można utworzyć niestandardową sekwencję przejść za pomocą klawisza Tab z pominięciem pól, które nie są potrzebne w takiej sekwencji. Aby uzyskać więcej informacji dotyczących personalizacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).

![Opcja „Rozszerzona sekwencja użycia klawisza Tab”](media/8c0f12bbb3f26032997ef0ba95d89b6a.png  "Opcja „Rozszerzona sekwencja użycia klawisza Tab”")

## <a name="form-patterns"></a>Wzorce formularzy

Prawie 90 procent stron w produkcie opiera się na niewielkim zestawie wzorców. Wzorce te są nazywane *wzorcami formularzy*. Każdy wzorzec formularza uwzględnia akcje, które są wykonywane na stronie najczęściej. Wzorzec formularza pozwala umożliwia zaznajomienie się użytkownika ze stroną i ułatwia jej zrozumienie, ponieważ często używane akcje i dane są zawsze widoczne w tym samym miejscu na różnych stronach. Ze względu na małą liczbę wzorców formularzy użytkownicy mogą w łatwy sposób nauczyć się systemu, niezależnie od liczby jego stron i po zapoznaniu się z wzorcami formularzy mogą się po nim poruszać bezproblemowo.

Aby uzyskać więcej informacji na temat wzorców formularzy zobacz [Style i wzorce formularzy](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Elastyczny układ

Ten produkt jest przeznaczony do pracy na różnych urządzeniach i przy różnych współczynnikach formularzy, od najmniejszych ekranów do dużych ekranów o najwyższej rozdzielczości. Nasz aparat odpowiadający za elastyczny układ umożliwia użytkownikom powiększanie do poziomu 200 procent (a w niektórych scenariuszach nawet ponad 200 procent).

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Wytyczne dotyczące podejścia z uwzględnieniem ułatwiania dostępu w swoich konfiguracjach niestandardowych dla programistów i klientów

Aby uzyskać więcej informacji na temat najlepszych praktyk firmy Microsoft w zakresie ułatwiania dostępu, zobacz [Ułatwienia dostępu w formularzach, produktach i kontrolkach](../../dev-itpro/user-interface/enable-accessibility.md).

