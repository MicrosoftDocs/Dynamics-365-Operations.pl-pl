---
title: Praca z plikami zastępowania CSS
description: W tym temacie opisano, dlaczego, kiedy i jak używać plików zastępowania kaskadowych arkuszy stylów (CSS) w aplikacji Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6788481936a54bff32096dba1d0424fc52c669e4
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964611"
---
# <a name="work-with-css-override-files"></a>Praca z plikami zastępowania CSS

[!include [banner](includes/banner.md)]

W tym temacie opisano, dlaczego, kiedy i jak używać plików zastępowania kaskadowych arkuszy stylów (CSS) w aplikacji Microsoft Dynamics 365 Commerce.

Stałe style witryny zazwyczaj powinny być obsługiwane za pośrednictwem motywu witryny. Motywy udostępniają podstawowe ustawienia stylów CSS i ustawienia stylów dla modułów na dowolnej stronie witryny. Motywy są tworzone przy użyciu zestawu Dynamics 365 Commerce SDK (Software Development Kit) w trybie online i są wdrażane w witrynach internetowych za pośrednictwem usług Microsoft Dynamics Lifecycle Services (LCS). Możliwości debugowania modułu i konfiguracje interfejsu modułu w zestawie SDK pomagają deweloperom tworzyć dostosowywalne i spójne pakiety projektów witryny. Gdy te pakiety projektów są wdrażane w witrynie, autorzy witryn mogą skupić się na tworzeniu, edytowaniu i publikowaniu zawartości, a nie na programowaniu witryny.

Biorąc pod uwagę zwykły cykl życia motywu, zależność od tego, aby deweloperzy zmienili styl za pomocą zestawu SDK i potoku wdrażania usługi LCS może stanowić element zaporowy w niektórych scenariuszach. Prototypy lub poprawki witryny mogą wydawać się kłopotliwe, jeśli zestaw SDK nie jest skonfigurowany lub jeśli nie masz czasu na oczekiwanie na wdrożenie usługi LCS.

W tych scenariuszach mogą pomóc pliki zastępowania CSS. W narzędziach autorskich usługi Commerce uwierzytelnieni użytkownicy mogą przekazać plik CSS, wyświetlić jego podgląd, a następnie aktywować go w celu zastąpienia motywu witryny. Obciążenie związane z wdrożeniem zestawu SDK lub usługi LCS nie jest wymagane. Zastąpienia, które są określone w pliku zastępowania CSS, mogą być tak małe, jak zmiana stylu pojedynczego tekstu, lub szeroko zakrojone, na przykład kompletna przebudowa marki.

Przed użyciem plików zastępowania CSS pamiętać o następujących ograniczeniach:

- Tylko jeden plik zastępowania CSS może być aktywny w danej witrynie w danym momencie. W związku z tym wszystkie aktywne zastąpienia muszą być obecne w pojedynczym pliku zastępowania.
- Chociaż podgląd zastąpień można wyświetlać w narzędziach autorskich usługi Commerce, nie ma żadnych dedykowanych funkcji debugowania, które pomogą zidentyfikować błędy wprowadzane przez zastąpienia. Innymi słowy, jeśli używasz plików zastępowania CSS, nie masz tego samego zestawu narzędzi, który zawiera zestaw SDK do weryfikowania modułu i procesu tworzenia.

Niemniej jednak pliki zastępowania CSS oferują szybki sposób tworzenia prototypu projektu lub implementowania poprawki, zanim zostanie opracowana i zaimplementowana pełna aktualizacja motywu.

## <a name="create-a-css-override-file"></a>Tworzenie pliku zastępowania CSS

Aby utworzyć plik zastępowania CSS, można użyć dowolnego zintegrowanego środowiska projektowego (IDE), edytora tekstów lub edytora kodu źródłowego. Typowym podejściem jest użycie standardowych debugerów internetowych w przeglądarce do identyfikowania selektorów stylów, właściwości i wartości w istniejącej witrynie. Większość przeglądarek umożliwia zmienianie wartości i wyświetlanie ich podglądu w debugerze. Po zidentyfikowaniu zmian, które chcesz wprowadzić, można zapisać je we własnym pliku CSS.

## <a name="upload-a-css-override-file"></a>Przekazywanie pliku zastępowania CSS

Aby przekazać plik CSS do witryny w usłudze Commerce, wykonaj następujące kroki.

1. W narzędziach autorskich przejdź do swojej witryny.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**.

    > [!NOTE]
    > W zależności od wersji narzędzi autorskich usługi Commerce, których używasz, być może trzeba rozwinąć pozycję **Ustawienia** w okienku nawigacji, aby można było wybrać pozycję **Projekt**.

1. W górnej części głównego okienka projektu wybierz kartę **Zastępowanie CSS**, jeśli nie jest jeszcze wybrana.
1. W obszarze **Dostępne zastąpienia CSS** wybierz pozycję **Przekaż plik CSS**. Zostanie wyświetlone okno Eksploratora plików.
1. W Eksploratorze plików przejdź do pliku CSS i zaznacz go, a następnie wybierz pozycję **Otwórz**. Przekazany plik CSS pojawi się teraz w obszarze **Dostępne zastąpienia CSS**.

## <a name="preview-a-css-override-file"></a>Wyświetlanie podglądu pliku zastępowania CSS

Aby wyświetlić podgląd pliku zastępowania CSS przed uaktywnieniem go w aktywnej witrynie, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**, a następnie na karcie **Zastępowanie CSS** w obszarze **Dostępne zastąpienia CSS** znajdź plik CSS, którego podgląd chcesz wyświetlić.
1. Obok nazwy pliku CSS wybierz opcję **Podgląd witryny**.
1. W oknie dialogowym **Wybieranie adresu URL** wybierz adres URL witryny, dla której chcesz zobaczyć zastosowane zastąpienie, a następnie wybierz przycisk **OK**.
1. Jeśli istnieje wiele wariantów wybranego adresu URL, wybierz żądany wariant w wyświetlonym oknie dialogowym **Podgląd wariantów**.

Zostanie otwarta nowa karta lub okno przeglądarki, w którym możesz zweryfikować zastąpienia stylu względem witryny. Następnie możesz udostępnić adres URL innym uwierzytelnionym użytkownikom usługi Commerce w celu przejrzenia i przesłania opinii.

## <a name="activate-a-css-override-file-on-your-live-site"></a>Aktywowanie pliku zastępowania CSS w aktywnej witrynie

Po wyświetleniu podglądu i zatwierdzeniu pliku zastępowania CSS można go aktywować w aktywnej witrynie.

> [!NOTE]
> Tylko jeden plik zastępowania CSS może być aktywny w Twojej witrynie w danym momencie. Jeśli uaktywnisz nowy plik zastępowania, poprzedni plik zastępowania zostanie wyłączony. W związku z tym upewnij się, że wszystkie wymagane zastąpienia są obecne w pojedynczym pliku zastępowania CSS.

Aby aktywować pliki zastępowania CSS, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**, a następnie na karcie **Zastępowanie CSS** w obszarze **Dostępne zastąpienia CSS** znajdź plik CSS, który chcesz aktywować.
1. W obszarze nazwy pliku CSS wybierz pozycję **Aktywuj**. Plik zastępowania natychmiast uaktywni się w Twojej aktywnej witrynie.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>Dezaktywowanie pliku zastępowania CSS w aktywnej witrynie

Aby dezaktywować plik zastępowania CSS w witrynie, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Projekt**, a następnie na karcie **Zastępowanie CSS** w obszarze **Dostępne zastąpienia CSS** znajdź plik CSS, który chcesz dezaktywować.
1. W obszarze nazwy pliku CSS wybierz pozycję **Dezaktywuj**. Plik zastępowania natychmiast zostanie wyłączony w Twojej aktywnej witrynie.

> [!TIP]
> Aby uzyskać dostęp do dodatkowych opcji plików zastępowania CSS, wybierz wielokropek (**...**) obok nazwy pliku CSS. Opcje **pobierania**, **zmieniania nazwy** i **zastępowania** są przydatne w przypadku szybkich zmian w istniejącym pliku zastępowania CSS.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Praca z predefiniowanymi ustawieniami stylów](style-presets.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
