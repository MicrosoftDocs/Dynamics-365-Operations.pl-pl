---
title: Grupy konfiguracji rozwiązania Invoice Capture
description: Ten artykuł zawiera ogólne informacje o grupach konfiguracji w rozwiązaniu Invoice Capture.
author: sunfzam
ms.date: 09/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691219"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Grupy konfiguracji rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Użytkownicy mogą zarządzać listą pól faktur oraz ustawieniem ręcznego przeglądu osób prawnych za pomocą grup konfiguracji. Użytkownicy mogą ustawiać konfiguracje faktur dla różnych osób prawnych w grupach. Wszystkie osoby prawne w tej samej grupie konfiguracji korzystają z tych samych pól faktury i ustawień przeglądu ręcznego.

## <a name="manage-configuration-groups"></a>Zarządzanie grupami konfiguracji

Aby zarządzać grupami konfiguracji za pomocą aplikacji, przejdź do pozycji **Ustawienia**, a następnie wybierz **Konfiguracja systemu \> Definiowanie składnika konfiguracji systemu**.

Na stronie **Definiowanie grup konfiguracji** na karcie głównej jest wyświetlana lista zdefiniowanych grup konfiguracji. Pokazuje ona także domyślną grupę konfiguracji. Dla każdej grupy konfiguracji dostępne są następujące akcje:

- **Kopiowanie grupy konfiguracji** — nową grupę konfiguracji można utworzyć, duplikując istniejącą grupę. Nowa grupa ma takie same wartości, jak oryginalna grupa dla wszystkich pól, z wyjątkiem pól **Nazwa grupy** i **Opis grupy**. Po zduplikowaniu grupy konfiguracji wybierz przycisk **OK**.
- **Usuwanie grupy konfiguracji** — aby usunąć grupę konfiguracji, zaznacz ją, a następnie wybierz polecenie **Usuń**.

    > [!NOTE]
    > Nie można usunąć domyślnej grupy konfiguracji.

- **Edytowanie identyfikatora grupy konfiguracji** — aby edytować identyfikator grupy konfiguracji, wybierz pole **Identyfikator grupy** i zaktualizuj wartość. Identyfikator grupy nie może zawierać spacji ani znaków specjalnych, a jego długość nie może przekraczać 20 znaków.

    > [!NOTE]
    > Wartość pola **Identyfikator grupy** można zaktualizować tylko raz.

- **Edytowanie opisu grupy konfiguracji** — aby edytować opis grupy konfiguracji, wybierz pole **Opis** i zaktualizuj wartość.
- **Zmiana ustawienia przeglądu ręcznego** — użytkownicy mogą zdecydować, czy fakturę trzeba przejrzeć ręcznie. Aby zmienić ustawienie przeglądu ręcznego, wybierz opcję **Wymagaj przeglądu ręcznego**. Dostępne są następujące opcje:

    - **Zawsze przegląd ręczny** — tę opcję należy wybrać, jeśli faktury w grupie konfiguracji zawsze wymagają przeglądu ręcznego.
    - **W przypadku błędów i ostrzeżeń** — tę opcję należy wybrać, jeśli faktury zawierające komunikaty o błędach lub komunikaty ostrzegawcze wymagają przeglądu ręcznego.
    - **W przypadku błędów** — tę opcję należy wybrać, jeśli faktury zawierające komunikaty o błędach wymagają przeglądu ręcznego.

- **Zmień ustawienie współczynnika ufności** — współczynnik ufności to metadane wykorzystywane przez rozwiązanie Invoice Capture, które umożliwia zgłaszanie dokładności rozpoznanych danych faktur. Im wyższy współczynnik, tym dokładniejsze mogą być rozpoznawane dane. Konfiguracja umożliwia użytkownikom zdefiniowanie wymaganego przeglądu ręcznego na podstawie współczynnika ufności. Użytkownicy mogą zmienić próg współczynnika ufności dla faktur. Aby zaktualizować ustawienie współczynnika ufności, wybierz pole **Współczynnik ufności** i zaktualizuj wartość.

    Istnieją dwa typy alertów dla współczynników ufności:

    - **Ostrzeżenie** — pola faktur, których współczynnik ufności przekracza próg ostrzeżenia, są traktowane jako poprawne. Próg ostrzeżenia musi być większy niż próg błędu i mniejszy niż 100.
    - **Błąd** — pola faktur, których współczynnik ufności jest mniejszy niż próg błędu, są traktowane jako pola z błędem. Komunikaty o błędzie będą wyświetlane dla użytkowników. Próg błędu musi być większy niż 0 (zero) i mniejszy niż próg ostrzeżenia. Komunikaty ostrzegawcze będą wyświetlane dla pól faktur ze współczynnikami ufności między progiem ostrzeżenia a progiem błędu.

- **Zarządzaj polami faktur** — użytkownicy mogą zarządzać listą pól faktur, która jest wyświetlana w przeglądarce dokumentów obok siebie. Na karcie **Zarządzanie polami faktury** wybierz symbol koła zębatego, wybierz pola faktury do dodania, a następnie wybierz pozycję **Zapisz**. Wybrane pola zostaną dodane do listy. Aby usunąć pole faktury z listy, wybierz w polu opcję **Usuń**.

### <a name="manage-file-filters-optional"></a>Zarządzanie filtrami plików (opcjonalne)

Zarządzanie filtrami plików umożliwia użytkownikom definiowanie dodatkowych filtrów dla przychodzących plików faktur. Pliki, które nie spełniają kryteriów filtrowania zostaną odebrane i będą wyświetlane na liście **Otrzymane pliki**, ale będą pokazywać błędy walidacji plików. To zachowanie różni się od zachowania filtrów zdefiniowanych w kanale. W przypadku tych filtrów pliki, które nie spełniają kryteriów, w ogóle nie zostaną odebrane. Użytkownicy mogą przeglądać pliki przychodzące i decydować, czy każdy plik jest nieprawidłowym plikiem faktury, a następnie mogą oznaczyć plik jako przestarzały plik lub ręcznie uwzględnić go w celu rozpoznania i uwzględnienia w przechwyconych fakturach.

Po zainstalowaniu rozwiązania Invoice Capture jest definiowany domyślny filtr plików. Ten filtr plików jest globalny. Jeśli ustawienia filtru mają być inne, możesz zaktualizować domyślny filtr. Jeśli pole jest wymagane, wybierz opcję **Wymagane**. 

### <a name="accepted-file-size"></a>Akceptowany rozmiar pliku

Można wybrać akceptowany rozmiar pliku.

> [!NOTE]
> Pliki o rozmiarze większym niż 20 480 kilobajtów (KB) nie są obsługiwane.

### <a name="supported-file-types"></a>Obsługiwane typy plików

Obecnie obsługiwane są następujące typy plików:

- PDF
- PNG
- JPG
- JPEG
- TIF
- Plik TIFF
