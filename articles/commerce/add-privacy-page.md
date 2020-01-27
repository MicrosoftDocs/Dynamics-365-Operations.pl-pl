---
title: Dodawanie strony zasad ochrony prywatności
description: W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fd39ff5f8c5d97f2d524043b65627dc7e87fcf64
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946067"
---
# <a name="add-a-privacy-policy-page"></a>Dodawanie strony zasad ochrony prywatności

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Zgodność z zasadami ochrony prywatności obejmuje środki organizacyjne, które informują użytkowników witryny o sposobie gromadzenia i zbierania ich danych. Użytkownicy mogą zdecydować, w jaki sposób mają być przetwarzane dane osobowe, i mogą podejmować odpowiednie akcje.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>Przeczytaj zasady ochrony prywatności Microsoft w aplikacji Dynamics 365 Commerce

Aby przeczytać zasady ochrony prywatności Microsoft po zalogowaniu do narzędzi autorskich Dynamics 365 Commerce, wybierz przycisk **Pomoc** (**?**) w prawym górnym rogu, a następnie wybierz pozycję **Prywatność i pliki cookie**. Zostanie otwarta nowa karta z linkiem do [oświadczenia o ochronie prywatności Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Tworzenie strony zasad ochrony prywatności dla witryny

W aplikacji Dynamics 365 Commerce istnieje kilka sposobów udostępniania użytkownikom witryny zasad ochrony prywatności. W tej sekcji przedstawiono sposób tworzenia strony zasad ochrony prywatności, a następnie odwoływania się do tej strony za pomocą fragmentu stopki.

Poniższe wskazówki to przykład, który pokazuje, jak utworzyć stronę ogólnych zasad ochrony prywatności dla witryny usługi Commerce. Odpowiadasz za zaprojektowanie i zaimplementowanie rozwiązania strony polityki prywatności, które najlepiej spełnia wymagania prawne Twojej firmy.

Aby rozpocząć, w narzędziach autorskich przejdź do witryny, dla której chcesz utworzyć stronę zasad ochrony prywatności.

### <a name="create-a-template"></a>Utwórz szablon

> [!NOTE]
> Jeśli szablon, który może być użyty na stronie zasad ochrony prywatności, został już utworzony, przejdź do sekcji [Tworzenie strony zasad ochrony prywatności](#build-a-privacy-policy-page).

Aby utworzyć szablon, należy wykonać poniższe kroki.

1. Przejdź do pozycji **Szablony \> Nowy szablon**.
1. Wprowadź nazwę szablonu, a następnie kliknij przycisk **OK**.
1. W szablonie dodaj wszystkie wymagane moduły do wymaganych gniazd stron. Aby uzyskać wskazówki, najedź kursorem na czerwone wykrzykniki.

    Na przykład miejsce **Nagłówek HTML** może wymagać modułu **Domyślny skrypt zewnętrzny”**.

1. W miejscu **Treść** dodaj moduł **Strona domyślna**.
1. W module **Strona domyślna** w miejscu **Główne** dodaj moduł **Blok zawartości zaawansowanej**.
1. W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.
1. Zaewidencjonuj szablon i opublikuj go.

### <a name="build-a-privacy-policy-page"></a>Tworzenie strony zasad ochrony prywatności

Aby utworzyć stronę zasad ochrony prywatności, wykonaj następujące kroki.

1. Przejdź do **Strony \> Nowa strona**.
1. Wybierz szablon strony zasad ochrony prywatności.
1. Wprowadź nazwę i adres URL strony, a następnie wybierz przycisk **OK**. 
1. W miejscu **Główne** na stronie dodaj moduł **Blok zawartości zaawansowanej**.
1. W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.
1. W okienku właściwości modułu **Blok zawartości zaawansowanej** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość tekstu sformatowanego**.
1. W edytorze tekstu sformatowanego wprowadź zawartość strony zasad ochrony prywatności. W razie potrzeby rozwiń edytor tekstu sformatowanego do trybu pełnoekranowego.
1. Po zakończeniu wprowadzania zawartości wybierz pozycję **Podgląd**, aby wyświetlić podgląd strony w przeglądarce internetowej.
1. Zakończ wszystkie pozostałe operacje dodawania do właściwości strony i modułu.
1. Zaewidencjonuj stronę zasad ochrony prywatności i opublikuj ją.

Aby opublikować adres URL strony zasad ochrony prywatności, wykonaj następujące kroki.

1. Przejdź do obszaru **Adresy URL** i wybierz adres URL strony zasad ochrony prywatności.
1. Publikowanie wybranego adresu URL

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Tworzenie linku do strony zasad ochrony prywatności w stopce

Do fragmentu można dodać link do strony zasad ochrony prywatności. W ten sposób można udostępnić link i zaktualizować go na wielu stronach witryny, odwołując się do fragmentu. W tym przykładzie pokazano, jak dodać link do strony zasad ochrony prywatności do fragmentu stopki.

Aby dodać link do fragmentu stopki, wykonaj następujące kroki.

1. Przejdź do pozycji **Fragmenty strony \> Nowy fragment strony**.
1. Wybierz moduł **Stopka**, a następnie wprowadź nazwę w polu **Nazwa fragmentu strony**.
1. W miejscu **Kategoria stopki** dodaj moduł **Element stopki**.
1. W panelu właściwości po prawej stronie wybierz pozycję **Tekst linku**.
1. W oknie dialogowym **Tekst linku** wprowadź tekst linku i docelowy link strony zasady ochrony prywatności, a następnie kliknij przycisk **OK**.

    Aby uzyskać adres URL strony zasad ochrony prywatności, przejdź do obszaru **Strony**, przejdź do strony zasad ochrony prywatności i skopiuj adres URL z okienka właściwości.

1. Zapisz fragment, zaewidencjonuj go i opublikuj.
1. Wyświetl podgląd fragmentu i przetestuj link do strony zasad ochrony prywatności.

Teraz można odwoływać się do fragmentu w szablonie dla innych stron witryny. Gdy ten fragment jest przywoływany w module **Stopka** szablonu, odwołanie do linku pojawi się na wszystkich stronach, które zostaną zbudowane przy użyciu tego szablonu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zgodności](compliance-overview.md)

[Funkcje i możliwości dostępności](accessibility.md)

[Zgodność z plikami cookie](cookie-compliance.md)
