---
title: Funkcje i możliwości dostępności
description: Ten temat zawiera informacje na temat funkcji i możliwości ułatwień dostępu w usłudze Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6f6bca3589da4055eef000fc3b2c88b93eabb4d5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414862"
---
# <a name="accessibility-features-and-capabilities"></a>Funkcje i możliwości dostępności


[!include [banner](includes/banner.md)]

Ten temat zawiera informacje na temat funkcji i możliwości ułatwień dostępu w usłudze Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Funkcje i możliwości ułatwień dostępu umożliwiają wszystkim użytkownikom dostęp do akcji i ich wykonywanie ich, dzięki czemu mogą osiągać założone cele. Ten szeroki zakres użytkowników może wymagać narzędzi wspomagających dla słuchu, wzroku, mobilności lub neuroróżnorodności.

Różne funkcje aplikacji Dynamics 365 Commerce umożliwiają kompilowanie witryny tak, aby zawierała funkcje pomocnicze. Podczas projektowania witryny należy wziąć pod uwagę obszary funkcji ułatwień dostępu, które są wymienione w [centrum ułatwień dostępu Microsoft](https://www.microsoft.com/accessibility). 

W tym temacie opisano niektóre dodatkowe obszary funkcji ułatwień dostępu, które należy wziąć pod uwagę podczas korzystania z aplikacji Dynamics 365 Commerce.

## <a name="image-alt-text"></a>Tekst alternatywny obrazu

Aplikacja Dynamics 365 Commerce ma wbudowany system zarządzania zasobami cyfrowymi do śledzenia zasobów graficznych i wideo, które są używane w Twojej witrynie. Podpisy, opisy i tekst alternatywny obrazów można dodawać w okienku właściwości obrazu, gdy jest on wybrany lub przesyłany.

## <a name="video-accessibility"></a>Ułatwienia dostępu do zawartości wideo

System zarządzania zasobami cyfrowymi aplikacji Dynamics 365 Commerce obsługuje kilka funkcji ułatwień dostępu dla zawartości wideo. Niektóre przykłady znajdują się w poniższej tabeli.

| Funkcja wideo               | Opis |
|-----------------------------|-------------|
| Napisy      | Tekst, który może być wyświetlany dla dźwięku i opisowych elementów dźwiękowych w filmie wideo, aby pomóc użytkownikom niedosłyszącym i slabosłyszących |
| Podtytuły                   | Pliki napisów, które pokazują tekst wskazówek kontekstowych lub okna dialogowego na ekranie |
| Transkrypcje dźwiękowe           | Tekstowa transkrypcja wypowiadanych słów generowana na podstawie dźwięku z zasobu wideo |
| Dźwięk opisowy           | Niepodstawowy kanał audio, który opisuje zawartość lub kontekst występujące na ekranie |
| Minimalna bramka wiekowa            | Atrybut, w którym można przechowywać minimalny wiek osoby, która może oglądać film wideo (tylko metadane) |

### <a name="configure-video-accessibility-elements"></a>Konfigurowanie elementów ułatwień dostępu do zawartości wideo

W aplikacji Commerce w sekcji **Biblioteka multimedialna** możesz przesyłać zasoby wideo, które mają oddzielne pliki napisów, dźwięku zwykłego i dźwięku opisowego. Napisy mogą być również generowane automatycznie po przekazaniu elementu zawartości wideo.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>Generowanie lub przekazywanie plików napisów podczas przekazywania elementu zawartości wideo

Aby plik napisów został automatycznie wygenerowany podczas przekazywania pliku wideo, wykonaj ten krok.

- W oknie dialogowym **Przekazywanie elementów zawartości** wybierz opcję **Automatycznie generuj napisy**. Jeśli generujesz plik napisów, selektor plików dla plików napisów nie będzie dostępny w oknie dialogowym.

Aby ręcznie przekazać plik napisów podczas przekazywania pliku wideo, wykonaj ten krok.

- W oknie dialogowym **Przekazywanie elementów zawartości** wyczyść zaznaczenie opcji **Automatycznie generuj napisy**.

Aby przekazać pliki dźwięku zwykłego lub dźwięku opisowego dla wideo, użyj selektora plików w oknie dialogowym **Przekazywanie elementów zawartości**.

> [!NOTE]
> Elementy zawartości, takie jak napisy, dźwięk zwykły i dźwięk opisowy, można również dodać po przekazaniu elementu zawartości wideo. Przejdź do obszaru **Biblioteka multimedialna** wybierz elementy zawartości wideo, wybierz **Edytuj** i wyewidencjonuj go. Następnie w okienku właściwości dla elementu zawartości wideo przekaż dodatkowe elementy zawartości.

#### <a name="edit-cc-and-audio-transcript-files"></a>Edytowanie plików napisów i transkrypcji dźwiękowej

Pliki napisów i transkrypcji dźwiękowej można edytować bezpośrednio w narzędziu do tworzenia zawartości. Odtwarzanie wideo jest dostępne podczas edycji.

Aby edytować pliki napisów i transkrypcji dźwiękowej, wykonaj następujące kroki.

1. Przejdź do **Biblioteki multimediów** i wybierz nazwę pliku zasobów wideo. Zostanie wyświetlony edytor zawartości napisów i transkrypcji.
1. Wybierz opcję **Edycja**.
1. Edytuj tekst napisów lub transkrypcji.
1. Po zakończeniu wybierz pozycję **Zapisz**, a następnie wybierz pozycję **Zakończ edycję**.
1. Gdy wszystko będzie gotowe do opublikowania, wybierz pozycję **Opublikuj**.

#### <a name="set-the-minimum-age-attribute"></a>Ustawianie atrybutu wieku minimalnego

Atrybut metadanych **Wiek minimalny** można skojarzyć z elementami zawartości wideo.

Aby ustawić atrybut **Wiek minimalny** dla elementu zawartości wideo, wykonaj następujące kroki.

1. Przejdź do sekcji **Biblioteka multimediów** i wybierz element zawartości wideo.
1. Wybierz opcję **Edycja**.
1. W okienku właściwości dla elementu zawartości wideo ustaw atrybut **Wiek minimalny**.

> [!NOTE]
> Okienko właściwości jest używane tylko do ustawiania i przechowywania wartości atrybutów metadanych. Aby użyć tego atrybutu do ustalania bramek odtwarzania, należy utworzyć moduły niestandardowe.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Ułatwienia dostępu w formularzach, produktach i kontrolkach](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Centrum ułatwień dostępu Microsoft](https://www.microsoft.com/accessibility)

[Centrum ułatwień dostępu Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/accessibility/index)

[Omówienie zgodności](compliance-overview.md)

[Zgodność z plikami cookie](cookie-compliance.md)

[Dodawanie strony zasad ochrony prywatności](add-privacy-page.md)

[Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]