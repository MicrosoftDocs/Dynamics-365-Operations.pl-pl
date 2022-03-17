---
title: Kopiowanie witryny handlu elektronicznego
description: W tym temacie opisano sposób kopiowania istniejącej witryny w portalu e-commerce w środowisku e-commerce lub między nimi w Konstruktorze witryn Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 284a33099fecc5a8e8d5d5d31612abab51735773
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2022
ms.locfileid: "8386983"
---
# <a name="copy-an-e-commerce-site"></a>Kopiowanie witryny handlu elektronicznego

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym temacie opisano sposób kopiowania istniejącej witryny w portalu e-commerce w środowisku e-commerce lub między nimi w Konstruktorze witryn Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce umożliwia kopiowanie i kopiowanie witryn jako samodzielnych operacji w Konstruktorze witryn portalu Commerce. Witryny można kopiować w jednym środowisku e-commerce lub między dwoma środowiskami handlu elektronicznego. Użytkownik, który zainicjował operację kopiowania witryny, musi być administratorem dzierżawy w źródłowym i docelowym środowisku e-commerce.

Operacja kopiowania witryny kopiuje całą zawartość witryny źródłowej w portalu e-commerce. Zawiera ona strony, fragmenty, szablony, adresy URL i elementy zawartości. Aby można było używać nowego lokacji, należy zainicjować go przy użyciu procesu pierwszego uruchomienia (FRE). Kanały można mapować i zarządzać nimi w narzędziu do tworzenia witryn, w **Ustawienia witryny \> kanały**.

Czas trwania operacji kopiowania w lokacji zależy głównie od liczby środków trwałych w lokacji źródłowej. W przypadku bardzo dużych witryn zaleca się rozważenie użycia w zamian operacji kopiowania środowiska. Ta operacja jest znana jako operacja portowalności danych.

> [!NOTE]
> - Witryna źródłowa będzie tylko do odczytu w czasie trwania operacji kopiowania witryny.
> - Kopiowane są tylko wersje opublikowane dokumentów. Jeśli nie zostały opublikowane żadne wersje, kopiowane są tylko najnowsze wersje.
> - Historia wersji zawartości nie będzie dostępna w witrynie docelowej.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Kopiowanie witryny w środowisku e-commerce

Aby skopiować witrynę w środowisku e-commerce, wykonaj następujące kroki.

1. Zaloguj się do Konstruktora witryn, aby uzyskać środowisko, w którym ma zostać wykonać operację kopiowania.
1. Aby otworzyć widok listy witryn, wybierz Opcję **Przełączania witryn** w prawym górnym rogu, a następnie wybierz pozycję **Zarządzaj witrynami**.
1. Znajdź witrynę, którą chcesz skopiować lub sklonować, i zaznacz ją, zaznaczając pole wyboru obok nazwy witryny.
1. W okienku akcji wybierz opcję **Kopiuj witrynę**.
1. W oknie dialogowym **Kopiuj witrynę** w polu **Nowa nazwa witryny** wprowadź nazwę witryny. Nowa nazwa witryny musi być unikatowa w środowisku e-commerce. Pola **Dzierżawa źródłowa** i **Witryna źródłowa** są automatycznie ustawiane na informacje dotyczące bieżącej dzierżawy i wybranej witryny.
1. Wybierz **Utwórz kopię**.

Po weryfikacji informacji powiadomienie wskazuje, że zostało utworzone nowe zadanie kopiowania witryny. Możesz monitorować postęp zadania w prawym [okienku strony **Zadania dzierżawcy**](#monitor-the-site-copy-operation). Po pomyślnym zakończeniu operacji kopiowania nowa witryna pojawi się na liście witryn w widoku listy witryn.

Poniższa ilustracja przedstawia przykład okna dialogowego **Kopiuj witrynę** w narzędziu do tworzenia witryn.

![Okno dialogowe Kopiuj witrynę w kreatorze witryn.](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Skopiuj witrynę między dwoma środowiskami e-commerce

Aby skopiować witrynę między dwoma środowiskami handlu elektronicznego, wykonaj następujące kroki.

1. Zaloguj się do kreatora witryn w docelowym środowisku e-commerce.
1. W okienku akcji wybierz opcję **Kopiuj witrynę**.
1. W oknie dialogowym **Kopiuj witrynę** w polu **Nowa nazwa witryny** wprowadź nazwę witryny. Nowa nazwa witryny musi być unikatowa w środowisku e-commerce.
1. W polu **Dzierżawa źródłowa** wybierz nazwę dzierżawy źródłowej.
1. W polu **Witryna źródłowa** wybierz witrynę źródłową.
1. Wybierz **Utwórz kopię**.

> [!NOTE]
> Uprawnienia administratora dzierżawców są wymagane w źródłowym i docelowym środowisku e-commerce.

Po weryfikacji informacji powiadomienie wskazuje, że zostało utworzone nowe zadanie kopiowania witryny. Możesz monitorować postęp zadania w prawym [okienku strony **Zadania dzierżawcy**](#monitor-the-site-copy-operation). Po pomyślnym zakończeniu operacji kopiowania nowa witryna pojawi się na liście witryn w widoku listy witryn.

## <a name="monitor-the-site-copy-operation"></a>Monitorowanie operacji kopiowania w lokacji

Aby monitorować postęp operacji kopiowania witryny, wykonaj następujące kroki.

1. Zaloguj się do kreatora witryn w docelowym środowisku e-commerce.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Zadania dzierżawcy**.
1. Na stronie **Zadania dzierżawcy** znajdź i wybierz zadanie kopiowania witryny na liście. Po prawej stronie zostanie wyświetlone okienko z informacjami o stanie i szczegółach wybranego zadania.

Możesz anulować zadanie o stanie **W toku**. Wybierz zamówienie na liście wyników, a następnie wybierz opcję **Anuluj** w okienku.

Można ponowić próbę wykonania zadania o stanie **Niepowodzenie** lub **Zakończone z błędami**. Wybierz zamówienie na liście wyników, a następnie wybierz opcję **Spróbuj ponownie** w okienku.

> [!NOTE]
> Przetwarzanie zasobów wideo może być kontynuowane po ukończeniu zadania kopiowania w witrynie.

Poniższa ilustracja przedstawia przykład prawego okienka strony **Zadania dzierżawców** w narzędziu do tworzenia witryn.

![Szczegóły zadania w prawym okienku strony Zadania dzierżawcy w Konstruktorze witryn.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Inicjuj nowy witrynę za pomocą procesu FRE

Aby można było korzystać z nowej witryny, należy ją zainicjować w procesie FRE.

Aby zainicjować nowy witrynę za pomocą procesu FRE, wykonaj następujące kroki.

1. Zaloguj się do konstruktora witryn dla nowej witryny.
1. Aby otworzyć widok listy witryn, wybierz Opcję **Przełączania witryn** w prawym górnym rogu, a następnie wybierz pozycję **Zarządzaj witrynami**.
1. Znajdź i wybierz nową witrynę, którą chcesz zainicjować.
1. W oknie dialogowym **Konfiguracja witryny** w polu **Wybierz domenę** wybierz domenę. Do wyboru są wszystkie domeny skojarzone ze środowiskiem e-commerce podczas inicjowania.
1. W polu **Wybierz kanał domyślny** wybierz powiązany kanał sklepu internetowego. Wybrany kanał będzie dostarczał asortymentów i innych informacji przechowywanych w programie Commerce Headquarters.
1. W polu **Wybierz domyślny język** wybierz domyślny język autorski. Do wyboru są wszystkie języki skonfigurowane dla wybranego kanału sklepu internetowego.
1. W polu **Ścieżka** wartość składa się z domeny podstawowej i opcjonalnej ścieżki URL, którą można wprowadzić. Ścieżkę adresu URL można pozostawić pustą, jeśli kanał będzie obsługiwany z katalogu głównego domeny lub jeśli chcesz wprowadzić te informacje później w widoku konfiguracji kanału w narzędziu do tworzenia witryn. Ścieżka witryny musi być unikalna w środowisku e-commerce.
1. Kliknij przycisk **OK**. Witryna jest inicjowana przy użyciu podanych informacji i ponownie jest zlokalizowany w widoku zarządzania witryną.

Poniższa ilustracja przedstawia przykład okna dialogowego **Skonfiguruj swoją witrynę** w narzędziu do tworzenia witryn.

![Skonfiguruj okno dialogowe witryny w narzędziu do tworzenia witryn.](media/site-copy_3.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-b2c-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
