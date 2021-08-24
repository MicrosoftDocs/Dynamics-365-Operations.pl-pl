---
title: Zarządzanie plikami robots.txt
description: W tym temacie opisano sposób zarządzania plikami robots.txt w aplikacji Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: e1078de354a96cc50b7c1b79a864db5041ea5069df650670e65531faaeb32e0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754399"
---
# <a name="manage-robotstxt-files"></a>Zarządzanie plikami robots.txt

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób zarządzania plikami robots.txt w aplikacji Microsoft Dynamics 365 Commerce.

Standard wykluczenia robotów lub robots. txt to standard używany przez witryny internetowe do komunikowania się z robotami internetowymi. Instruuje on roboty internetowe o obszarach witryny, które nie powinny być odwiedzane. Roboty są często używane przez wyszukiwarki do indeksowania witryn internetowych.

Aby wykluczyć roboty z serwera, należy utworzyć plik na serwerze. W tym pliku należy określić zasady dostępu dla robotów. Plik musi być dostępny za pośrednictwem protokołu HTTP w lokalnym adresie URL **/robots.txt**. Plik robots.txt pomaga wyszukiwarkom indeksować zawartość witryny.

Aplikacja Dynamics 365 Commerce umożliwia przekazanie pliku robots.txt dla domeny. Dla każdej domeny w środowisku usługi Commerce można przekazać jeden plik robots.txt i skojarzyć go z tą domeną.

Więcej informacji na temat pliku robots.txt można znaleźć [na stronach robotów internetowych](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Przekazywanie pliku robots.txt

Po utworzeniu i edytowaniu pliku robots.txt zgodnie ze [standardem wykluczania robotów](https://www.robotstxt.org/orig.html) upewnij się, że plik jest dostępny na komputerze, na którym będą używane narzędzia autorskie usługi Commerce. Plik musi mieć nazwę **robots.txt**. Aby uzyskać najlepsze wyniki, musi być on w formacie, który jest odnotowany w standardzie. Każdy klient usługi Commerce jest odpowiedzialny za walidację i utrzymywanie zawartości pliku robots.txt. Aby przekazać plik robots.txt, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.

Aby przekazać plik robots.txt w usłudze Commerce, wykonaj następujące kroki.

1. Zaloguj się do usługi Commerce jako administrator systemu.
2. W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.
3. W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**. Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.
4. Wybierz pozycję **Zarządzaj**, aby przekazać plik robots.txt dla domeny w danym środowisku.
5. W menu po prawej stronie wybierz przycisk **Przekaż** (strzałka wskazująca w górę) obok domeny skojarzonej z plikiem robots.txt. Zostanie wyświetlone okno dialogowe przeglądarki plików.
6. W oknie dialogowym znajdź i wybierz plik robots.txt, który chcesz przekazać dla skojarzonej domeny, a następnie wybierz pozycję **Otwórz**, aby ukończyć przekazywanie.

> [!NOTE] 
> Podczas przekazywania usługa Commerce sprawdza, czy plik jest plikiem tekstowym, ale nie weryfikuje zawartości pliku.

## <a name="download-a-robotstxt-file"></a>Pobieranie pliku robots.txt

Aby pobrać plik robots.txt w usłudze Commerce, wykonaj następujące kroki.

1. Zaloguj się do usługi Commerce jako administrator systemu.
2. W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.
3. W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**. Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.
4. Wybierz pozycję **Zarządzaj**, aby pobrać plik robots.txt dla domeny w danym środowisku.
5. W menu po prawej stronie wybierz przycisk **Pobierz** (strzałka wskazująca w dół) obok domeny skojarzonej z plikiem robots.txt. Zostanie wyświetlone okno dialogowe przeglądarki plików.
6. W oknie dialogowym przejdź do żądanej lokalizacji na dysku lokalnym, potwierdź lub wprowadź nazwę pliku, a następnie wybierz pozycję **Zapisz**, aby ukończyć pobieranie.

> [!NOTE]
> Tej procedury można używać do pobierania tylko plików robots.txt, które zostały wcześniej przekazane za pomocą narzędzi autorskich usługi Commerce.

## <a name="delete-a-robotstxt-file"></a>Usuwanie pliku robots.txt

Aby usunąć plik robots.txt w usłudze Commerce, wykonaj następujące kroki.

1. Zaloguj się do usługi Commerce jako administrator systemu.
2. W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.
3. W obszarze **Ustawienia dzierżawy** wybierz pozycję **Robots.txt**. Lista wszystkich domen skojarzonych z danym środowiskiem pojawia się w głównej części okna.
4. Wybierz pozycję **Zarządzaj**, aby usunąć plik robots.txt dla domeny w danym środowisku.
5. W menu po prawej stronie wybierz przycisk **Usuń** (symbol kosza) obok domeny skojarzonej z plikiem robots.txt. Zostanie wyświetlone okno przeglądarki plików.
6. W oknie przeglądarki plików znajdź i wybierz plik robots.txt, który chcesz usunąć dla domeny, a następnie wybierz pozycję **Otwórz**. Zostanie wyświetlone okno z komunikatem ostrzegawczym.
7. W oknie komunikatu wybierz pozycję **Usuń**, aby potwierdzić usunięcie pliku robots.txt.

> [!NOTE] 
> Tej procedury można używać do usuwania tylko plików robots.txt, które zostały wcześniej przekazane za pomocą narzędzi autorskich usługi Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w module Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
