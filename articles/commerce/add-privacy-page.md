---
title: Dodawanie strony zasad ochrony prywatności
description: W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 12cd0358279684ce1d3050348c37209ba3d29140
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797534"
---
# <a name="add-a-privacy-policy-page"></a>Dodawanie strony zasad ochrony prywatności

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać stronę zasad ochrony prywatności do witryny w Microsoft Dynamics 365 Commerce.

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

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć szablon strony.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon baneru promocyjnego**, a następnie wybierz **OK**.
1. W szablonie dodaj wszystkie wymagane moduły do wymaganych gniazd stron. Aby uzyskać wskazówki, najedź kursorem na czerwone wykrzykniki. (Na przykład miejsce **Nagłówek HTML** może wymagać modułu **Domyślny skrypt zewnętrzny**.)
1. W miejscu **Treść** dodaj moduł **Strona domyślna**.
1. W module **Strona domyślna** w miejscu **Główne** dodaj moduł **Blok zawartości zaawansowanej**.
1. W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="build-a-privacy-policy-page"></a>Tworzenie strony zasad ochrony prywatności

Aby utworzyć stronę zasad ochrony prywatności, wykonaj następujące kroki.

1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon strony zasady prywatności.
1. Wprowadź nazwę i adres URL strony, a następnie wybierz przycisk **OK**. 
1. W miejscu **Główne** na stronie dodaj moduł **Blok zawartości zaawansowanej**.
1. W module **Blok zawartości zaawansowanej** dodaj moduł **Element bloku zawartości zaawansowanej**.
1. W okienku właściwości modułu **Blok zawartości zaawansowanej** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość tekstu sformatowanego**.
1. W edytorze tekstu sformatowanego wprowadź zawartość strony zasad ochrony prywatności. W razie potrzeby rozwiń edytor tekstu sformatowanego do trybu pełnoekranowego.
1. Po zakończeniu wprowadzania zawartości wybierz pozycję **Podgląd**, aby wyświetlić podgląd strony w przeglądarce internetowej.
1. Zakończ wszystkie pozostałe operacje dodawania do właściwości strony i modułu.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Aby opublikować adres URL strony zasad ochrony prywatności, wykonaj następujące kroki.

1. Przejdź do obszaru **Adresy URL** i wybierz adres URL strony zasad ochrony prywatności.
1. Wybierz opcję **Publikuj**, aby opublikować wybrany adres URL.

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Tworzenie linku do strony zasad ochrony prywatności w stopce

Do fragmentu można dodać link do strony zasad ochrony prywatności. W ten sposób można udostępnić link i zaktualizować go na wielu stronach witryny, odwołując się do fragmentu. W tym przykładzie pokazano, jak dodać link do strony zasad ochrony prywatności do fragmentu stopki.

Aby dodać link do fragmentu stopki, wykonaj następujące kroki.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment strony.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Stopki**.
1. W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.
1. W miejscu **Kategoria stopki** dodaj moduł **Element stopki**.
1. W panelu właściwości po prawej stronie wybierz pozycję **Tekst linku**.
1. W oknie dialogowym **Tekst linku** wprowadź tekst linku i docelowy link strony zasady ochrony prywatności, a następnie kliknij przycisk **OK**.
1. Aby uzyskać adres URL strony zasad ochrony prywatności, przejdź do obszaru **Strony**, przejdź do strony zasad ochrony prywatności i skopiuj adres URL z okienka właściwości.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Wyświetl podgląd fragmentu i przetestuj link do strony zasad ochrony prywatności.

Teraz można odwoływać się do fragmentu w szablonie dla innych stron witryny. Gdy ten fragment jest przywoływany w module **Stopka** szablonu, odwołanie do linku pojawi się na wszystkich stronach, które zostaną zbudowane przy użyciu tego szablonu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zgodności](compliance-overview.md)

[Funkcje i możliwości dostępności](accessibility.md)

[Zgodność z plikami cookie](cookie-compliance.md)

[Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
