---
title: Moduł selektora katalogów
description: Ten artykuł omawia moduły kompletacji katalogów i opisuje, jak dodać je do witryn e-commerce Microsoft Dynamics 365 Commerce business-to-business (B2B).
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136948"
---
# <a name="catalog-picker-module"></a>Moduł selektora katalogów

[!include [banner](includes/banner.md)]

Ten artykuł omawia moduły kompletacji katalogów i opisuje, jak dodać je do witryn e-commerce Microsoft Dynamics 365 Commerce business-to-business (B2B).

Moduł wyboru katalogów to specjalny pojemnik, który służy do wyświetlania listy wszystkich katalogów produktów dostępnych dla użytkowników strony B2B w celu dokonania zakupów. Obsługa wielu katalogów jest obecnie dostępna tylko dla stron B2B.

Poniższa ilustracja przedstawia przykład modułu kompletacji katalogów.

![Przykład modułu wybierającego katalogi, który wymienia trzy katalogi produktów.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Dodaj do swojej witryny moduł wyboru katalogów

Aby dodać moduł wybierania katalogów do swojej witryny w kreatorze witryn Commerce, wykonaj poniższe kroki.

### <a name="create-a-catalog-picker-page"></a>Tworzenie strony wybierania katalogu

Najpierw utwórz stronę z wyborem katalogów.

1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Utwórz nowa stronę**, w obszarze **Nazwa strony** wprowadź **Wybieranie katalogów**.
1. W sekcji **URL strony** wprowadź adres URL strony, a następnie wybierz **Dalej**.

    ![Okno dialogowe Utwórz nową stronę.](./media/Create-catalog-picker-page.png)

1. W sekcji **Wybierz szablon** wybierz **Treść ogólna**, który utworzyłeś, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz układ** wybierz **Elastyczny układ**, który utworzyłeś, a następnie wybierz **Dalej**.
1. W sekcji **Przegląd i zakończenie** przejrzyj konfigurację strony. Jeśli chcesz edytować informacje na stronie, wybierz pozycję **Wstecz**. Jeśli informacje na stronie są poprawne, wybierz pozycję **Utwórz stronę**.
1. W gnieździe **Wybieranie katalogów** w **Strona domyślna** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.

    ![Dodanie modułu do gniazda głównego w selektorze katalogów.](./media/Author-web-page-catalog-picker-1.png)

1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. Wybierz **Pojemnik**, wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz modułu** wybierz moduł **Wybieranie katalogów** i wybierz przycisk **OK**.
1. W okienku właściwości **Wybieranie katalogów**, w **Nagłówku** wybierz **Katalogi**, a następnie wprowadź nagłówek dla strony wybierającej katalogi.
1. W **obszarze Poziom nagłówka** wybierz poziom nagłówka, a następnie wybierz **OK**.
1. W polu **Tekst sformatowany** wpisz tekst, który pojawi się w górnej części strony wybierającej katalogi.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="add-a-link-on-your-account-page"></a>Dodaj link na stronie swojego konta

Następnie dodaj odwołanie do strony wyboru katalogu na stronie **Moje konto**.

1. Przejdź do **strony**, znajdź i wybierz stronę **Moje konto** w swojej witrynie, a następnie wybierz pozycję **Edytuj**.
1. W gnieździe **Główne** strony wybierz gniazdo **Kafelek konta ogólne**. 
1. W okienku **Właściwości kafelków ogólnych** konta w obszarze **Łącza** wybierz opcję **Dodaj łącze akcji**, a następnie wybierz **łącze akcji**.
1. W oknie dialogowym **Łącze akcji**, pod **Tekstem łącza**, wprowadź tekst łącza do strony z wyborem katalogu.
1. W obszarze **Łącze do celu** wybierz pozycję **Dodaj łącze**.
1. W oknie dialogowym **Dodaj link** wybierz **Strona niestandardowa**, a następnie **Dalej**.
1. W obszarze **Nazwa** wybierz stronę selektora katalogu, wybierz przycisk **Zastosuj**, a następnie wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Poniższa ilustracja przedstawia przykład strony kont z odniesieniem do strony katalogu.

![Strona moich kont z linkiem do katalogu.](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Dodaj łącze z nagłówka

Na koniec dodaj link z nagłówka swojej strony do katalogów.

1. Przejdź do **Fragmentów**, znajdź i zaznacz fragment nagłówka swojej witryny, a następnie wybierz **Edytuj**.
1. Wybierz gniazdo **nagłówka**. 
1. W okienku **Nagłówek** konta w obszarze **Łącza do mojego konta** wybierz opcję **Dodaj łącze akcji**, a następnie wybierz **łącze akcji**.
1. W oknie dialogowym **Łącze akcji**, pod **Tekstem łącza**, wprowadź tekst łącza do strony z wyborem katalogu.
1. W obszarze **Łącze do celu** wybierz pozycję **Dodaj łącze**.
1. W oknie dialogowym **Dodaj link** wybierz **Strona niestandardowa**, a następnie **Dalej**.
1. W obszarze **Nazwa** wybierz stronę selektora katalogu, wybierz przycisk **Zastosuj**, a następnie wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment nagłówka, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Poniższa ilustracja przedstawia przykład nagłówka strony internetowej dla handlu elektronicznego z linkiem do katalogu B2B.

![Nagłówek strony internetowej Ecommerce z rozwijanym linkiem do katalogu.](./media/catalog-in-header.png)


## <a name="additional-resources"></a>Dodatkowe zasoby 

[Tworzenie katalogów Commerce dla stron B2B](catalogs-b2b-sites.md)

[Wpływ rozszerzalności katalogów Commerce na dostosowanie B2B](catalogs-b2b-sites-dev.md)

[Katalogi Commerce dla B2B FAQ](catalogs-b2b-sites-FAQ.md)

[Strony i moduły zarządzania kontem](account-management.md)

[Moduł nagłówka](author-header-module.md)
