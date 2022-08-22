---
title: Tworzenie niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx/5xx
description: W tym artykule opisano sposób tworzenia niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx i 5xx przy użyciu narzędzi autorskich Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4a3b1762cebc74c1b77f9ca60925608bc966e306
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276408"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Tworzenie niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx/5xx

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób tworzenia niestandardowych stron odpowiedzi dla błędów kodu stanu 4xx i 5xx przy użyciu narzędzi autorskich Microsoft Dynamics 365 Commerce.

Jeśli żądanie nie powiodło się, serwer wystawia odpowiedzi na błędy kodów stanu HTTP. Kod stanu 404 jest przechwytywany i zwracany, jeśli nie odnaleziono strony, a kod stanu 500 jest przechwytywany i zwracany w przypadku wystąpienia błędu serwera. W Dynamics 365 Commerce Użytkownicy aplikacji mogą budować niestandardowe strony odpowiedzi na kod błędu, które są pokazywane użytkownikom w odpowiedzi na te błędy.

## <a name="build-a-status-code-error-response-page"></a>Utwórz stronę odpowiedzi na błędy kodu stanu

Aby rozpocząć tworzenie strony odpowiedzi na błędy kodu stanu, wykonaj następujące kroki.

1. W preferowanej przeglądarce sieci Web zaloguj się do Dynamics 365 Commerce. 
1. Wybierz oddział, dla którego chcesz utworzyć stronę odpowiedzi na błędy kodu stanu 4xx/5xx.

### <a name="build-the-template"></a>Zbuduj szablon

Aby zbudować szablon strony odpowiedzi na błąd kodu stanu, wykonaj następujące kroki.

1. Przejdź do okna **Szablony**.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy szablon strony.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź nazwę nowego szablonu, a następnie wybierz **OK**.
1. Utwórz szablon na podstawie struktury, która ma być stroną odpowiedzi na błędy kodu stanu.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 

### <a name="build-the-status-code-error-response-page"></a>Utwórz stronę odpowiedzi na błędy kodu stanu

Aby utworzyć strony odpowiedzi na błędy kodu stanu, wykonaj następujące kroki.

1. Przejdź do **Strony**.
1. Wybierz **Nowy**, aby utworzyć stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon, a następnie w obszarze **Nazwa strony** wprowadź nazwę strony odpowiedzi na błędy kodu stanu. Pole **Adres URL strony** należy pozostawić puste.
1. Zbuduj stronę.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

> [!NOTE]
> Istnieje możliwość utworzenia oddzielnej strony odpowiedzi o błędy kodów stanu dla błędów kodu stanu 4xx i 5xx. Alternatywnie można skorzystać z tej samej strony odpowiedzi o błędzie o tym samym ogólnym kodzie stanu dla obu kategorii błędów.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Ustawianie przekierowywania dla strony odpowiedzi na błędy kodu stanu

Aby skonfigurować przekierowanie dla strony odpowiedzi na błąd kodu stanu, wykonaj następujące kroki.

1. Przejdź do **Adresy URL \> Nowy \> Nowy alias**, a następnie wybierz stronę odpowiedzi na błędy kodu stanu, która została utworzona wcześniej.
1. W polu **Alias** wprowadź wartość **domyślna-4xx** lub **domyślne-5xx**, zależnie od strony odpowiedzi na błędy kodu stanu, na której konfigurujesz przekierowanie. Te aliasy muszą zostać opublikowane. W przeciwnym razie przekierowanie nie będzie działać.
1. Wybierz przycisk **OK**, aby potwierdzić połączenie.

> [!NOTE]
> Jeśli w obu kategoriach błędów jest używana jedna strona odpowiedzi o błędzie kodu stanu, powtórz tę procedurę, aby połączyć alias z inną kategorią błędu na tej samej stronie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Praca z szablonami](work-with-templates.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Tworzenie adresu URL strony](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
