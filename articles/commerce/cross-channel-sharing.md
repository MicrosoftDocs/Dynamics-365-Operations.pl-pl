---
title: Włączanie i używanie udostępniania między kanałami
description: W tym artykule opisano sposób włączania i używania funkcji udostępniania między kanałami w kreatorze witryn programu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: c05da17327e61d6f61883ab97a403bf2cf8a68f1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270081"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Włączanie i używanie udostępniania między kanałami

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób włączania i używania funkcji udostępniania między kanałami w kreatorze witryn programu Microsoft Dynamics 365 Commerce.

Dzięki udostępnianiu między kanałami sprzedawcy mogą ponownie wykorzystać i udostępniać zawartość między wieloma kanałami oddziału. Ta funkcja jest przydatna w przypadku, gdy kanały oddziału mają zgodny język podstawowy lub wiele wspólnych elementów zawartości.

Udostępnianie między kanałami polega na włączeniu domyślnego kanału, który będzie przeszukiwany pod kątem dostępnej zawartości, gdy nie zostanie znaleziona wersja żądanej zawartości specyficznej dla kanału. Zawartość, która ma być współużytkowana między kanałami, jest tworzona w kanale domyślnym. Zawartość ta może być lokalizowana dla wszystkich ustawień regionalnych używanych w dowolnym kanale oddziału.

## <a name="when-to-use-cross-channel-sharing"></a>Kiedy korzystać z udostępniania między kanałami

Udostępnianie między kanałami jest przydatne, gdy wiele kanałów w jednym oddziale może udostępniać zawartość. Na przykład sprzedawca, który ma wiele marek i sklepów zgrupowanych w jednym oddziale, może udostępniać część zawartości niektórych lub wszystkich sklepów. Ta udostępniona zawartość może zawierać strony dotyczące warunków i postanowień, warunków płatności, metod wysyłki i często zadawanych pytań (FAQ).

W ramach udostępniania między kanałami są również obsługiwane fragmenty. Dlatego strona zawartości zawierająca fragmenty specyficzne dla kanału może zostać utworzona jako zawartość między kanałami. W takim przypadku większość zawartości zostanie udostępniona między kanałami, fragmenty określone dla kanału na stronie obejmującej kilka kanałów będą widoczne tylko na żądanie odpowiedniego kanału sklepu.

Oddziały, które mają tylko jeden kanał lub nie mają wielu kanałów, które nie mogą udostępniać zawartości, nie korzystają z udostępniania między kanałami.

## <a name="enable-cross-channel-sharing"></a>Włączanie udostępniania między kanałami

Udostępnianie między kanałami jest włączone na poziomie oddziału. Ta operacja jest jednokierunkowa. Innymi słowy, po włączeniu udostępniania między kanałami nie można go wyłączyć.

Aby włączyć udostępnianie między kanałami w konstruktorze witryn Commerce, należy wykonać następujące kroki.

1. Przejdź do **Ustawienia witryny \> Funkcje**.
1. Ustaw funkcję **Między kanałami** na wartość **Włączone**.

    ![Opcja między kanałami ustawiona na Włączone w kreatorze witryn Commerce.](./media/enabling-cross-channel-sharing.png)

Po włączeniu funkcji udostępniania między kanałami informacje będą wyświetlane w sekcji **Kanały** w **Ustawienia witryny \> Funkcje** jak pokazano na przykładzie przedstawionym na poniższej ilustracji.

![Informacje o kanałach widoczne po włączeniu udostępniania między kanałami.](./media/channels-cross-channel.png)

Ponadto po włączeniu funkcji udostępniania między kanałami pole **Kanał** w prawym górnym rogu kreatora witryn Commerce będzie zawierać opcję **Sklep internetowy dla kilku kanałów**, która może być używana do zarządzania zawartością między kanałami, jak to pokazano na poniższej ilustracji.

![Opcja Sklep internetowy dla kilku kanałów w polu Kanały po włączeniu udostępniania między kanałami.](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Tworzenie i używanie zawartości między kanałami

Zawartość między kanałami można tworzyć i stosować na wiele sposobów. Można na przykład tworzyć fragmenty między kanałami, tworzyć strony między kanałami, które używają zawartości między kanałami i specyficznej dla kanału oraz zastępować fragmenty między kanałami wersjami fragmentów specyficznych dla kanału.

### <a name="create-a-cross-channel-fragment"></a>Tworzenie fragmentu między kanałami

Aby utworzyć fragment między kanałami w konstruktorze witryn Commerce, należy wykonać następujące kroki.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Transparent promocyjny**, a następnie w obszarze **Nazwa fragmentu** wprowadź nazwę (na przykład **Transparent między kanałami**). Następnie wybierz opcję **OK**.
1. W okienku właściwości modułu **Banner promocyjny** wybierz opcję **Dodaj wiadomość**, a następnie wybierz opcję **Wiadomość**.
1. W oknie dialogowym **Komunikat**, w obszarze **Tekst** wprowadź wartość **Między kanałami**, a następnie kliknij przycisk **OK**. 
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Ten fragment między kanałami może być używany w stronach między kanałami lub specyficznych dla kanału, które są tworzone w dowolnym kanale witryny.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Tworzenie strony między kanałami, która używa zawartości między kanałami

Strony między kanałami mogą być używane w dowolnym kanale danego oddziału. Można więc utworzyć stronę udostępnione zawartości jednorazowo i wykonać wszystkie kolejne aktualizacje w jednym miejscu. Na przykład strona **Warunki i zasady** między kanałami, która ma adres URL `/toc`, może być udostępniona wszystkim kanałom oddziału. Jeśli podstawowe adresy URL dla kanałów oddziału to `www.fabrikam.com/brand1` i `www.fabrikam.com/brand2`, ta sama udostępniona strona międzykanałowa **Warunki i zasady** będzie dostępna zarówno z poziomu adresów URL kanału witryny, odpowiednio `www.fabrikam.com/brand1/toc` i `www.fabrikam.com/brand2/toc`. Jeśli strona **Warunki i zasady** musi zostać zaktualizowana później, należy zaktualizować tylko jedną stronę udostępnioną.

Aby utworzyć w kreatorze witryn Commerce stronę międzykanałową, w której jest używana zawartość między kanałami, wykonaj następujące kroki.

1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon, na przykład **Marketing**.
1. W obszarze **Nazwa strony** wprowadź nazwę strony (na przykład **Strona między kanałami**).
1. W obszarze **Adres URL strony** wprowadź adres URL strony (na przykład **examplepage**), a następnie wybierz **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj fragment**.
1. W oknie dialogowym **Dodawanie fragmentu** wybierz wcześniej utworzony fragment międzykanałowy, który ma transparent promocyjny, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Powinien być widoczny transparent promocyjny o treści „Między kanałami”.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Tworzenie strony specyficznej dla kanału, która używa zawartości między kanałami

Korzystając z zawartości między kanałami na stronach specyficznych dla kanału, można utworzyć pojedyncze fragmenty udostępnionej zawartości, a następnie używać ich na stronach specyficznych dla kanału. To „pojedyncze źródło” jest przydatne w przypadku zawartości udostępnionej, takiej jak warunki i zasady, warunki płatności lub informacje kontaktowe.

Aby utworzyć w kreatorze witryn Commerce stronę specyficzną dla kanału, w której jest używana zawartość między kanałami, wykonaj następujące kroki.

1. Z poziomu określonego kanału, na przykład **Rozszerzony sklep online Fabrikam** przejdź do **Strony**, a następnie wybierz opcję **Nowa**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon, na przykład **Marketing**.
1. W obszarze **Nazwa strony** wprowadź nazwę strony (na przykład **Strona specyficzna dla kanału**).
1. W obszarze **Adres URL strony** wprowadź adres URL strony (na przykład **channelspecificpage**), a następnie wybierz **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj fragment**.
1. W oknie dialogowym **Dodawanie fragmentu**, w obszarze **Kanał**, zaznacz opcję **Sklep internetowy między kanałami**. Utworzony wcześniej fragment między kanałami powinien pojawić się na liście. Zaznacz go i wybierz **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Powinien być widoczny transparent promocyjny o treści „Między kanałami”.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Tworzenie specyficznej dla kanału wersji strony międzykanałowej

Udostępnianie między kanałami obsługuje zastąpienia zawartości między kanałami. Na przykład wszystkie kanały witryny oprócz jednego mają tę samą część zawartości. Ten jeden kanał witryny wymaga innej zawartości. Aby zaimplementować inną zawartość, należy zastąpić zawartość międzykanałową zawartością specyficzną dla kanału, tworząc specyficzną dla kanału wersję strony międzykanałowej.

Aby utworzyć w kreatorze witryn Commerce specyficzną dla kanału wersję strony międzykanałowej, wykonaj następujące kroki.

1. W polu **Kanał** w prawym górnym rogu wybierz opcję **Sklep internetowy między kanałami**.
1. Otwórz utworzoną wcześniej stronę między kanałami.
1. W polu **Kanał** w prawym górnym rogu wybierz kanał, który powinien mieć określoną zawartość. W edytorze stron zostanie wyświetlony komunikat z monitem o utworzenie nowego wariantu strony.
1. Wybierz opcję **Utwórz wariant strony**.
1. W gnieździe **Głównym** wariantu strony wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Baner promocyjny** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Banner promocyjny** wybierz opcję **Dodaj wiadomość**, a następnie wybierz opcję **Wiadomość**.
1. W oknie dialogowym **Komunikat**, w obszarze **Tekst** wprowadź wartość **Specyficzne dla kanału**, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Powinien być widoczny transparent promocyjny o treści „Specyficzny dla kanału”.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

W przypadku użycia podstawowego adresu URL kanału i przejścia do adresu URL strony międzykanałowej w tym oddziale zostanie wyświetlona zawartość dla kanału, a nie zawartość międzykanałowa.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Sposoby dodawania zawartości](add-manage-content.md)

[Słownik terminów dotyczących modelu strony](page-elements-overview.md)

[Dokumentowanie stanów i cyklów życia](document-states-overview.md)

[Praca z grupami publikowania](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
