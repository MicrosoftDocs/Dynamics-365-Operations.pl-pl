---
title: Pozycje
description: W tym temacie opisano elementy pojęć, które mogą uwzględniać stanowisko. Zawiera również przykłady, które pokazują, jak można używać tych elementów w organizacji.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c8311df31326faeadd280585115338317b19125d54f3a526b4ccc6ef6684ad2c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754759"
---
# <a name="positions"></a>Pozycje

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano elementy pojęć, które mogą uwzględniać stanowisko. Zawiera również przykłady, które pokazują, jak można używać tych elementów w organizacji.

Aby można było utworzyć stanowisko, należy skonfigurować stanowisko. Niektóre szczegóły dotyczące stanowiska, takie jak region wynagrodzenia, przydział pracownika, czas trwania stanowiska i relacja sprawozdawcza, mają datę wejścia w życie.

## <a name="general-information"></a>Informacje ogólne

Podczas tworzenia stanowiska należy wybrać stanowisko. Dla wybranego zadania zostaną automatycznie wypełnione następujące informacje:

- opis
- Nazwa
- W przeliczeniu na pełne etaty
- Rodzina zadania

Stanowisko jest używane w celu odwołania do stanowiska pracownika. (Nie jest używany tytuł wymieniony w danych pracownika) W związku z tym tytuły stanowisk powinny być standardowane tak, jak to możliwe.

> [!NOTE]
> Pracownik nie może zostać przydzielony do stanowiska w dniu, który przypada przed datą dostępności do przydziału.
>
> Parametr na karcie **Stanowiska** na stronie **Udostępniane parametry zasobów ludzkich** kontroluje zachowanie przypisania pracownika. Należy wybrać jedną z następujących opcji:
>
> - **Zawsze** — Można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk. Podczas tworzenia stanowisk data i godzina w obszarze **Dostępne do przypisania** na karcie **Ogólne** na stronie **Stanowisko** są automatycznie ustawiane na datę i godzinę utworzenia.
> - **Nigdy** — nie można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk. W przypadku wybrania tej opcji należy otworzyć stronę **Stanowisko** dla każdego nowego stanowiska, gdy będzie ono dostępne. Następnie, na karcie **Ogólne**, wprowadź datę **dostępnego przypisania**, aby włączyć przypisanie pracownika. W przypadku wybrania tej opcji podczas próby przypisania pracownika data przypisania pracownika zostanie ustawiona domyślnie na **Nigdy**.

## <a name="position-duration"></a>Okres ważności stanowiska

Każda pozycja obowiązuje przez określony czas, który jest określany jako czas trwania. Na przykład letnie stanowiska mogą mieć czas trwania od 1 maja 2021 r. do 31 sierpnia 2021 r. Datą aktywacji jest data, kiedy pozycja jest aktywna w systemie. Data przejścia na emeryturę to moment, w którym pozycja nie jest już aktywna w systemie.

Należy pamiętać, że ani data dostępności do przydziału, ani data przypisania pracownika nie może być wcześniejsza niż data aktywacji. Pozycja nie jest uznawana za aktywną do czasu osiągnięcia daty aktywacji. Ponadto przypisanie pracownika nie może zmienić daty przejścia na emeryturę dla tego stanowiska.

## <a name="reports-to-position"></a>Stanowisko zwierzchnie

Pozycje są ważnymi elementami dla niższego poziomu hierarchii organizacji. Na stronie **Stanowiska** można określać pozycje nadrzędne. Podczas przypisywania pracownika do pozycji podrzędnej względem innej pozycji, tworzy się relację raportowania między pracownikami przypisanymi do tych dwóch miejsc. Na przykład stanowisko 000220 zgłasza się do stanowiska 000300. Kim Akers zostaje przydzielona do stanowiska 000220, a Sanjay Patel zostaje przydzielony do stanowiska 000300. Dlatego Kim Akers podlega Sanjayowi Patelowi.

> [!TIP]
> Stanowisko podrzędne jest używane w całym systemie do określenia, kto jest przełożonym danego pracownika. W poprzednim przykładzie, jeśli Sanjay Patel ma w systemie przypisaną rolę menedżera, to w Samoobsłudze Menedżera będzie widział Kim Akers jako bezpośredniego podwładnego. Relacja podrzędna może być również wykorzystywana przy tworzeniu reguł routingu przepływu pracy oraz zadań kontrolnych.

## <a name="relationships"></a>Relacje

Jeśli organizacja korzysta z hierarchii macierzowej lub innej niestandardowej hierarchii, można skonfigurować typy hierarchii stanowisk. Następnie można dodać relacje raportowania do pozycji dla każdego typu hierarchii, który został skonfigurowany. Na przykład Lori Penor jest kierownikiem głównym w Adventure Works i jest przypisana do pozycji **Kierownik główny**. Zarządza rozwojem produktu służącego do czyszczenia widżetów. Wymaga, aby księgowy pomagał jej w finansach. W związku z tym prosi Kim Akers, by był jej księgowym. Kim raportuje bezpośrednio do Sanjay Patel, ale współpracuje również z Lori Penor nad pracą, która jest związana z finansami dla rozwoju aplikacji do czyszczenia widżetów.

W poprzednim przykładzie należy wykonać następujące zadania, aby skonfigurować relację roboczą między Kim Akers i Lori Penor:

1. Utworzyliśmy niestandardowy typ pozycji o nazwie **Widżet**, by stworzyć hierarchię obejmującą pozycje dla osób pracujących przy projekcie programu do czyszczenia widżetów.
2. Przypisaliśmy pozycję **Kierownika głównego** jako nadrzędne względem pozycji Kim w hierarchii **Widżet**.
3. Hierarchia pozycji służy do wyświetlania struktury relacji służbowych pozycji. Jeśli masz wiele hierarchii pozycji, można wyświetlić hierarchię dla każdego typu hierarchii w hierarchii pozycji. Można też wyszukiwać pozycje według identyfikatora lub nazwy pracownika, który jest przypisany do pozycji. Hierarchia pozycji jest hierarchią organizacyjną.

## <a name="labor-union"></a>Związek zawodowy

Można zarejestrować, czy umowa związkowa jest wymagana dla tego stanowiska i jaka jest związek zawodowym. Umowę można także skojarzyć z podmiotem prawnym.

## <a name="financial-dimensions"></a>Wymiary finansowe

Podczas tworzenia wymiaru finansowego dla stanowiska należy określić podmiot prawny. Wymiary domyślne można wybierać indywidualnie dla poszczególnych wymiarów. Można również wybrać szablon dystrybucji, który będzie automatycznie wypełniał wymiary domyślne. Szablon dystrybucji udostępnia również opcję alokowania kwot w wielu wartościach wymiarów.
