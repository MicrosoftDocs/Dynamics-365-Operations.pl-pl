---
title: Tworzenie pól niestandardowych i praca z nimi
description: W tym temacie opisano, jak program Microsoft Dynamics 365 for Finance and Operations pozwala niektórym użytkownikom tworzyć niestandardowe pola w celu dostosowania aplikacji do unikatowych potrzeb firmy.
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 18402579789c17de7b46dd7a013b3b6327ea5d4f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "348027"
---
# <a name="create-and-work-with-custom-fields"></a>Tworzenie pól niestandardowych i praca z nimi

[!include [banner](../includes/banner.md)]

Program Microsoft Dynamics 365 for Finance and Operations zawiera już w standardzie rozbudowany zestaw pól do zarządzania różnorodnymi procesami biznesowymi, ale czasami firma musi śledzić dodatkowe informacje w systemie. W reakcji na tę potrzebę program Finance and Operations pozwala tworzyć niestandardowe pola w celu dostosowania aplikacji do specyfiki firmy, o ile tylko masz uprawnienia wobec tej funkcji.

Opcja dodawania pól niestandardowych jest dostępna w aktualizacji platformy 13 i nowszych wersjach.

W tym nagraniu wideo przedstawiono, jak łatwe jest do dodawanie niestandardowego pola do strony: [Dodawanie pól niestandardowych w Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Tworzenie pól niestandardowych

Po stwierdzeniu, które dodatkowe informacje mają być śledzone w aplikacji, można utworzyć niestandardowe pole w odpowiedniej tabeli, po czym udostępnić je na stronie.

Kroki poniżej opisują proces tworzenia niestandardowego pola i umieszczania go w formularzu.

1. Przejdź do formularza, w którym jest potrzebne nowe pole.
2. Ponieważ ostatecznym celem jest uwidocznienie niestandardowego pola w formularzu, punkt wejścia tworzenia niestandardowych pól znajduje się wewnątrz środowiska personalizacji. Otwórz pasek narzędzi personalizacji, wybierając kolejno polecenia **Opcje** i **Personalizuj ten formularz**.
3. Kliknij kolejno opcje **Wstaw** i **Pole**.
4. Wybierz region formularza, w którym nowe pole ma być wyświetlane. Po zaznaczeniu regionu w oknie dialogowym **Wstaw pola** zostanie wyświetlona lista istniejących pól, które można wstawić do wybranego regionu.
5. Upewnij się, że interesujące Cię pole jeszcze nie występuje na liście. Jeśli występuje, możesz po prostu zaznaczyć je na liście i kliknąć przycisk **Wstaw**.
6. Nad listą kliknij przycisk **Utwórz nowe pole**, aby zainicjować proces tworzenia pola niestandardowego. Spowoduje to otwarcie okna dialogowego **Utwórz nowe pole**.

    Jeśli nie widać przycisku **Utwórz nowe pole**, nie masz uprawnień niezbędnych do korzystania z tej funkcji.

7. W oknie dialogowym **Utwórz nowe pole** wprowadź następujące informacje.

    1. Wybierz tabelę bazy danych, do której powinno zostać dodane to pole. Należy zauważyć, że na liście rozwijanej będą wyświetlane tylko tabele, które obsługują niestandardowe pola. Sekcja poniżej zawiera szczegółowe informacje techniczne o obsługiwanych tabelach.
    2. Wybierz typ danych dla nowego pola. Dostępne typy danych to Pole wyboru, Data, Data i godzina, Liczba dziesiętna, Liczba, Lista wyboru i Tekst.

        - Jeśli wybrano typ danych Tekst, można również określić maksymalną długości tekstu, jaki można wprowadzić w tym polu.
        - W przypadku wybrania typu danych Lista wyboru można także wybrać zestaw prawidłowych wartości dla pola.

    3. Wprowadź nazwę, etykietę i tekst pomocy dla pola. Nazwa odpowiada fizycznej nazwie pola w bazie danych, podczas gdy etykieta i tekst pomocy to teksty używane do reprezentowania tego pola w interfejsie użytkownika.

8. Jeśli jest to jedyne pole, które trzeba utworzyć dla tego formularza, kliknij przycisk **Zapisz**. Jeśli trzeba utworzyć dodatkowe pola, kliknij przycisk **Zapisz i nowy**, a następnie wróć do kroku 7. Należy zauważyć, że obecnie istnieje limit **20 niestandardowych pól na każdą tabelę**.
9. Opuszczenie okna dialogowego **Utwórz nowe pole** spowoduje powrót do okna dialogowego **Wstaw pola**. Wszystkie właśnie dodane pola niestandardowe zostaną automatycznie oznaczone na liście pól jako przeznaczone do wstawienia do formularza.
10. Kliknij przycisk **Wstaw**, aby wstawić oznaczone pola do wybranego regionu formularza.
11. **Opcjonalnie:** Na pasku narzędzi personalizacji włącz tryb **Przenieś**, aby przenieść nowe pola w żądane miejsce w wybranym regionie. Zobacz temat [Dostosowanie do użytkownika](personalize-user-experience.md), aby uzyskać więcej informacji na temat używania różnych funkcji personalizacji w celu dostosowania formularza do własnych potrzeb.

## <a name="sharing-custom-fields-with-other-users"></a>Udostępnianie niestandardowych pól innym użytkownikom

Po utworzeniu niestandardowego pola i jego uwidocznieniu w formularzu można innym użytkownikom w systemie udostępnić zaktualizowany widok strony zawierający nowe pole. Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:

- Zalecanym sposobem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników. Aby uzyskać więcej informacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).
- Alternatywnie można wyeksportować swoje zmiany (nazywane *personalizacjami*), wysłać do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany. Opcja **Zarządzaj** umieszczona na pasku narzędzi personalizacji umożliwia eksportowanie i importowanie personalizacji.

## <a name="managing-custom-fields"></a>Zarządzanie polami niestandardowymi

Zarządzanie wszystkimi polami niestandardowymi w systemie można realizować za pomocą strony **Pola niestandardowe** w module Administrowanie systemem. Ta strona umożliwia użytkownikom dostęp do wielu funkcji, takich jak:

- Wyświetlanie listy wszystkich niestandardowych pól w systemie.
- Ograniczone edytowanie istniejących pól niestandardowych.
- Usuwanie pól niestandardowych.
- Udostępnianie niestandardowych pól w jednostkach danych.
- Tłumaczenie etykiet i tekstów pomocy pól niestandardowych.

### <a name="viewing-all-custom-fields"></a>Wyświetlanie wszystkich pól niestandardowych

Strona **Pola niestandardowe** umożliwia podgląd wszystkich pól niestandardowych, które zostały zdefiniowane w systemie. Po prostu zaznacz tabelę, która Cię interesuje, a strona zostanie zaktualizowana, pokazując listę pól niestandardowych skojarzonych z tą tabelą. Wybranie pola niestandardowego z listy pozwoli wyświetlić wszystkie szczegółowe informacje o polu.

### <a name="editing-custom-fields"></a>Edytowanie pól niestandardowych

Po utworzeniu pola niestandardowego tylko niektóre informacje o tym polu można modyfikować na stronie **Pola niestandardowe**.

*Można* modyfikować następujące atrybuty:

- Etykiety
- Tekst pomocy
- Długość w przypadku pól tekstowych

*Nie można* edytować następujących atrybutów:

- Nazwa pola
- Typ danych

Ponadto w przypadku pól list wyboru można zmienić kolejność zestawu prawidłowych wartości dla pola niestandardowego oraz dodać nowe wartości, ale nie można usunąć istniejących wartości pola listy wyboru. Pamiętaj, aby kliknąć przycisk **Zastosuj zmiany** po zakończeniu edytowania pól konkretnej tabeli, tak zmiany aby zostały zapisane.

### <a name="exposing-custom-fields-on-data-entities"></a>Udostępnianie niestandardowych pól w jednostkach danych

Może być również ważne, aby pola niestandardowe były wyświetlane w jednostkach danych. Jednostki danych są wykorzystywane w funkcji [Otwórz w aplikacji pakietu Office](../../dev-itpro/office-integration/office-integration.md), jak również w scenariuszach importu/eksportu danych.

Wykonaj poniższe czynności, aby włączyć wyświetlanie pola niestandardowego w jednostce danych:

1. Wybierz pole niestandardowe w formularzu **Pola niestandardowe**.
2. Rozwiń sekcję **Jednostki**, aby zobaczyć zestaw odnośnych jednostek.
3. Kliknij przycisk **Edytuj**.
4. Zmodyfikuj ustawienie pola **Włączone** w taki sposób, aby było wybierane dla każdej jednostki, w której ma być widoczne.
5. Kliknij przycisk **Zastosuj zmiany**, aby zapisać wybrane ustawienia.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Pozwalanie na wyświetlanie niestandardowych pól w innych językach

Ponieważ dostępu do pól niestandardowych mogą potrzebować użytkownicy posługujący się różnymi językami, strona **Pola niestandardowe** zawiera mechanizm umożliwiający tłumaczenie etykiety i tekstu pomocy pola niestandardowego na inne języki.

Kroki poniżej opisują proces tłumaczenia pól niestandardowych na inne języki:

1. Wybierz pole niestandardowe na stronie **Pola niestandardowe**.
2. W okienku akcji wybierz przycisk **Tłumaczenia**. Spowoduje to otwarcie menu rozwijanego z istniejącymi tłumaczeniami dla tego pola.
3. Menu rozwijane **Język** zawiera zestaw języków, dla których zostały już przygotowane tłumaczenia.

    Jeśli chcesz edytować istniejące tłumaczenie, wybierz żądany język z menu, a następnie zmodyfikuj wartości etykiety i tekstu pomocy.

    W przeciwnym razie kliknij przycisk **Dodaj język**, wybierz żądany język z menu, a następnie wprowadź wartości tłumaczeń dla etykiety i tekstu pomocy.

4. Po zakończeniu kliknij przycisk **OK**.

### <a name="deleting-custom-fields"></a>Usuwanie pól niestandardowych

W rzadkich przypadkach może się okazać, że pole niestandardowe nie jest już potrzebne. W takiej sytuacji administrator systemu może usunąć pole ze strony **Pola niestandardowe**. W tym celu upewnij się, że jest zaznaczone poprawne pole, kliknij przycisk **Usuń**, kliknij przycisk **Tak**, aby potwierdzić zamiar usunięcia, a na koniec kliknij przycisk **Zastosuj zmiany**.

> [!NOTE]
> Tej czynności nie będzie można cofnąć, a jej wynikiem będzie trwałe usunięcie danych skojarzonych z polem z bazy danych.

## <a name="appendix"></a>Dodatek

### <a name="who-can-create-custom-fields"></a>Kto może tworzyć pola niestandardowe?

Dla bezpieczeństwa systemu tylko administratorzy systemu mogą domyślnie tworzyć pola niestandardowe. Jeśli jednak organizacja uzna za konieczne, administrator systemu może niektórym użytkownikom zaawansowanym nadać prawo tworzenia niestandardowych pól, używając do tego roli **Użytkownik zaawansowany personalizacji środowiska uruchomieniowego**. Użytkownicy bez tej roli zabezpieczeń nie będą mogli tworzyć pól niestandardowych, ale będą widzieć pola niestandardowe dodane przez innych użytkowników w systemie oraz będą mogli z nich korzystać.

### <a name="what-tables-support-custom-fields"></a>Które tabele obsługują pola niestandardowe?

Ze względów wydajnościowych i technicznych obecnie pola niestandardowe można dodawać tylko do tabel spełniających następujące warunki.

- Tabela musi być oznakowana jako należąca do jednej z poniższych grup:

    - Grupa
    - WorksheetHeader
    - Główny
    - Różne
    - Parametr
    - Odwołanie
    - TransactionHeader

- Tabela nie może być rozszerzeniem innej tabeli.
- Tabela nie może być oznaczona jako systemowa.
- Tabela nie może być tymczasowa.
