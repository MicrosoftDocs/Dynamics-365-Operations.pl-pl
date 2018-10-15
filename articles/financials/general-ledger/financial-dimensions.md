---
title: Wymiary finansowe
description: "W tym temacie opisano różne typy wymiarów finansowych oraz sposoby ich konfigurowania."
author: aprilolson
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: d6b7b1219974cb5de1a625d87c3bce2a4439470b
ms.openlocfilehash: 9973d03de031ad2fa5647bb167c12b9231633a22
ms.contentlocale: pl-pl
ms.lasthandoff: 10/01/2018

---

# <a name="financial-dimensions"></a>Wymiary finansowe

[!include [banner](../includes/banner.md)]

W tym temacie omówiono różne typy wymiarów finansowych oraz sposoby ich konfigurowania.

Strona **Wymiary finansowe** umożliwia tworzenie wymiarów finansowych, które mogą być używane jako segmenty kont w planach kont. Istnieją dwa typy wymiarów finansowych: wymiary niestandardowe i wymiary oparte na jednostce. Niestandardowe wymiary są współużytkowane przez podmioty prawne i wartości są wprowadzane i obsługiwane przez użytkowników. W wymiarach opartych na jednostce wartości są zdefiniowane w innych miejscach w systemie, takich jak jednostki Odbiorcy lub Sklepy. Niektóre wymiary oparte na jednostce są współużytkowane przez podmioty prawne, podczas gdy inne są przypisane do określonej firmy.

Po utworzeniu wymiarów finansowych na stronie **Wartości wymiarów finansowych** przypisz dodatkowe właściwości do każdego wymiaru finansowego.

Wymiary finansowe mogą służyć do reprezentowania firm. Nie ma obowiązku tworzenia firm w programie Microsoft Dynamics 365 for Finance and Operations. Jednak wymiary finansowe nie są zaprojektowane do zaspokajania wymagań operacyjnych ani biznesowych firmy. Funkcję księgowania międzyjednostkowego w programie Finance and Operations zaprojektowano tylko z myślą o zapisach księgowych, które są tworzone przy każdej transakcji.

Przed skonfigurowaniem wymiarów finansowych jako firmy oceń swoje procesy biznesowe w następujących obszarach, aby ustalić, czy ta konfiguracja będzie działać w Twojej organizacji:

- Zapasy
- Sprzedaż i zakupy między wymiarami finansowymi i firmami
- Obliczanie i raportowanie podatku
- Raportowanie operacyjne

Poniżej przedstawiono wybrane ograniczenia:

- Można używać funkcji podatkowych tylko z firmami, a nie z wymiarami finansowymi.
- Niektóre raporty nie zawierają wymiarów finansowych. W związku z tym w celu raportowania według wymiarów finansowych może być konieczne modyfikowanie raportów.

## <a name="custom-dimensions"></a>Wymiary niestandardowe

Aby utworzyć zdefiniowany przez użytkownika typ wymiaru finansowego, w polu **Użyj wartości z** wybierz opcję **&lt;&nbsp;Wymiar niestandardowy&nbsp;&gt;**.

Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,. Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, na przykład litery lub łącznik (-). Można także wprowadzić znaki cyfr (\#) oraz handlowego „i” (&) jako symbole zastępcze znaków, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona. Znak cyfry (\#) służy jako symbol zastępczy dla cyfr, a znak handlowe „i” jako symbol zastępczy dla liter. Pole maski formatu jest dostępne tylko w przypadku zaznaczenia opcji **&lt;&nbsp;Wymiar niestandardowy&nbsp;&gt;** w polu **Użyj wartości z**.

**Przykład**

Aby ograniczyć wartość wymiaru do liter „CC” i trzech cyfr, należy wprowadzić **CC-\#\#\#** jako maskę formatu.

## <a name="entity-backed-dimensions"></a>Wymiary oparte na jednostce

Aby utworzyć wymiary oparte na jednostce, w polu **Użyj wartości z** wybierz jednostkę zdefiniowaną przez system, która będzie podstawą wymiaru finansowego. Wartości wymiarów finansowych będą wtedy tworzone na bazie tej jednostki. Na przykład aby utworzyć wartości wymiarów dla projektów, wybierz opcję **Projekty**. Wartość wymiaru zostanie wtedy utworzona dla każdej nazwy projektu. Strona **Wartości wymiarów finansowych** pokazuje wartości jednostki. Jeśli te wartości są związane z konkretną firmą, na stronie widać również firmę.

## <a name="activating-dimensions"></a>Aktywowanie wymiaru

Po uaktywnieniu wymiaru finansowego tabela zostanie zaktualizowana, tak aby zawierała nazwę wymiaru finansowego. Usunięte wymiary zostaną wykasowane. Wartości wymiaru finansowego można wprowadzić przed jego uaktywnieniem. Jednak wymiar finansowy będzie mógł być zużywany dopiero po uaktywnieniu. Na przykład, nie można dodać wymiaru finansowego do struktury konta przed aktywowaniem wymiaru finansowego. Po kliknięciu przycisku **Uaktywnij** wszystkie wymiary są aktualizowane i pokazują zmianę stanu.

## <a name="translations"></a>Tłumaczenia

Na stronie **Tłumaczenie tekstu** można wprowadzić tekst dla wybranego wymiaru finansowego w różnych językach. Na stronie **Tłumaczenie konta głównego** można wprowadzić tekst dla konta głównego w różnych językach. 

## <a name="legal-entity-overrides"></a>Firma zastępuje

Nie wszystkie wymiary mogą być używane we wszystkich firmach. Ponadto niektóre wymiary mogą mieć zastosowanie tylko do wybranych okresów. W takich przypadkach można w sekcji **Firma zastępuje** określić firmy, dla których wymiar powinien być zawieszony, właściciela oraz okres aktywności wymiaru.

## <a name="deleting-financial-dimensions"></a>Usuwanie wymiarów finansowych

Aby pomóc utrzymać więzy integralności danych, w wyjątkowych sytuacjach można usuwać wymiary finansowe. Jeśli zostanie podjęta próba usunięcia wymiaru finansowego, sprawdzane są następujące kryteria:

- Czy wymiar finansowy został użyty w jakiejkolwiek zaksięgowanej lub niezaksięgowanej transakcji albo w jakimkolwiek rodzaju kombinacja wartości wymiarów?
- Czy wymiar finansowy jest używany w jakiejkolwiek aktywnej strukturze konta, strukturze reguły zaawansowanej lub zestawie wymiarów finansowych?
- Czy wymiar finansowy wchodzi w skład domyślnego formatu integracji wymiarów finansowych?
- Czy wymiar finansowy ustawiono jako wymiar domyślny?

Jeśli którekolwiek z tych kryteriów jest spełnione, nie można usunąć wymiaru finansowego.

## <a name="default-dimension-values"></a>Wartości domyślne wymiarów

Wartości z rekordów głównych, takich jak rekordy odbiorców i dostawców, można używać jako wartości domyślnych w nowych wymiarach. Podczas tworzenia nowych wymiarów identyfikator rekordu głównego wprowadza się w wartościach wymiarów tych rekordów głównych. Na przykład podczas tworzenia nowego odbiorcy należy w wymiarze Odbiorca wprowadzić identyfikator odbiorcy. Podczas tworzenia zamówień sprzedaży, faktur i innych dokumentów wymagających identyfikatora odbiorcy są używane istniejące zasady ustawiania wartości domyślnych, a do dokumentu jest dodawany identyfikator odbiorcy.

Ta funkcja jest kontrolowana przez ustawienie w wymiarze. To ustawienie nosi nazwę **Kopiuj wartości do tego wymiaru dla każdej nowo tworzonej wartości DimensionName**, gdzie **DimensionName** jest nazwą wymiaru. Domyślnie ta funkcja jest wyłączona. Jednak można ją włączyć w dowolnym momencie.

Jeśli już istnieją rekordy dla wymiaru, włączenie funkcji spowoduje aktualizację głównych rekordów. Jednak istniejące dokumenty i transakcje nie zostaną zaktualizowane.

## <a name="derived-dimensions"></a>Wymiary pochodne

Wymiar można skonfigurować tak, aby informacje dla innych wymiarów były wprowadzane automatycznie podczas wprowadzania tego wymiaru w dokumencie. Na przykład jeśli wprowadzasz centrum kosztu 10, wartość **20** może być automatycznie wprowadzana w wymiarze Dział.

Na stronie Wymiary można skonfigurować wartości pochodne.

1. Wybierz wymiar, a następnie wybierz opcję **Wymiary pochodne**.

    Strona **Wymiary pochodne** zawiera siatkę. Wybrany segment wymiaru jest pierwszą kolumnę w tej siatce.

2. Dodaj segmenty, z których mają zostać utworzone obiekty pochodne. Każdy segment zostanie wyświetlony jako kolumna.

Wprowadź kombinacje wymiarów, które mają zostać utworzone jako pochodne wymiaru z pierwszej kolumny. Na przykład aby używać centrum kosztu jako wymiaru, z którego mają zostać utworzone wymiary pochodne Dział i Lokalizacja, wprowadź centrum kosztu 10, dział 20 i lokalizację 30. Następnie gdy wprowadzisz centrum kosztu 10 w rekordzie głównym lub na stronie transakcji, dział 20 i lokalizacja 30 zostaną wprowadzone domyślnie.

W procesie tworzenia wymiarów pochodnych nie są zastępowane istniejące wartości wymiarów pochodnych. Na przykład jeśli wprowadzisz centrum kosztu 10 i nie wprowadzisz żadnego innego wymiaru, domyślnie zostaną wprowadzone dział 20 i lokalizacja 30. Jednak jeśli zmienisz centrum kosztu, to wartości, które zostały już zdefiniowane, nie ulegną zmianie. W związku z tym można utworzyć wymiary domyślne w rekordach głównych, a wymiary te nie będą zmieniane przez wymiary pochodne.

### <a name="derived-dimensions-and-entities"></a>Pochodne wymiary i jednostki

Istnieje możliwość konfigurowania segmentów i wartości wymiarów pochodnych za pomocą jednostek.

- Jednostka Wymiary pochodne konfiguruje wymiary sterujące oraz segmenty, które są w nich używane.
- Jednostka DerivedDimensionValue umożliwia zaimportowanie wartości, które powinny zostać utworzone jako pochodne dla każdego wymiaru sterującego.

Jeżeli podczas używania jednostki do importowania danych ta jednostka importuje wymiary, podczas importowania są stosowane reguły wymiarów pochodnych, chyba że jednostka jednoznacznie spowoduje zastąpienie tych wymiarów.

Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Definiowanie wymiarów finansowych](tasks/define-financial-dimensions.md)
- [Obsługa domyślnych szablonów wymiaru finansowego](tasks/maintain-financial-dimension-default-templates.md)

