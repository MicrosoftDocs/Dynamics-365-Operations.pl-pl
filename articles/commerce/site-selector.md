---
title: Moduł selektora witryn
description: W tym artykule opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: efd58206d88618aedb6b574afb47da1e9e578ef1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276756"
---
# <a name="site-picker-module"></a>Moduł selektora witryn

[!include [banner](includes/banner.md)]

W tym artykule opisano moduł wyboru witryny i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Jeśli firma ma różne oddziały między rynkami, regionami i lokalizacjami, użytkownicy witryny muszą w prosty sposób przełączać się między witrynami i wybierać ich preferowaną witrynę w zakresie zakupów. Aby można było uwzględnić ten scenariusz, moduł wyboru witryn umożliwia przeglądanie użytkowników w wielu witrynach. Selektor witryn jest również zalecany w przypadku, gdy w witrynie sklepu internetowego zaimplementowano [funkcję wykrywania i przekierowania geograficznego](geo-detection-redirection.md), aby klienci mieli możliwość pominięcia preferencji witryny wskazanych przez nich za pomocą modułu [wyboru kraju/regionu](country-region-picker-module.md). 

Moduł selektora witryn musi być skonfigurowany z listą witryn (rynków, regionów lub ustawień regionalnych), które mogą przeglądać użytkownicy witryny. Na poniższej ilustracji przedstawiono przykład modułu wyboru witryny, który jest proponowany w nagłówku strony witryny.

![Przykład modułu wyboru witryn w nagłówku strony witryny.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Właściwości Modułu wyboru witryny

| Nazwa właściwości | Wartość                 | Opis |
|---------------|-----------------------|-------------|
| Nagłówek       | Tekst                  | Nagłówek modułu. |
| Opcje witryny  | Nazwa, obraz, adres URL      | Ta właściwość określa nazwę, łącze do strony głównej witryny oraz opcjonalny obraz, który ma być wyświetlany dla każdej witryny uwzględnionej w module. Obraz może być flagą lub pewną reprezentacją rynku, regionu lub ustawień regionalnych. |

## <a name="add-a-site-picker-module-to-a-page"></a>Dodawanie modułu wyboru witryny do nowej strony

Moduł selektora witryn można dodać do miejsca **selektora witryn** [modułu nagłówka](author-header-module.md). Po dodaniu modułu selektora witryn można zdefiniować nagłówek modułu i opcje witryny. Zazwyczaj moduł nagłówka znajduje się w fragmencie nagłówka, który można udostępnić na stronach portalu e-commerce dla witryny. 

Aby dodać moduł wyboru strony do modułu nagłówka, wykonaj poniższe kroki.

1. W gnieździe **Wybór witryny** w module nagłówka wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybór witryny** wybierz moduł **Wybór witryny** i wybierz przycisk **OK**.
1. W okienku właściwości **Wybór witryny** wybierz pozycję **Dodaj listę opcji witryny**. Zostanie wyświetlona edytowalna opcja **Lista opcji witryny**.
1. Wybierz **Lista opcji witryny**. Zostanie **wyświetlone okno dialogowe listy** opcji witryny.
1. W **obszarze Nazwa** witryny wprowadź tekst nazwy witryny, który będzie wyświetlany na liście rozwijanej stora witryn.
1. W obszarze **Adres URL przekierowywania** witryny wybierz **Dodaj łącze**. Zostanie wyświetlone wysuwane okienko **Dodaj link**.
1. W okienku wysuwanym **Dodaj link** wybierz **Strona niestandardowa**, a następnie **Dalej**.
1. Z listy adresów URL witryny wybierz adres URL ze ścieżką utworzoną podczas dodawania kanału do witryny (na przykład `www.adventure-works.com/fr-ca`), a następnie wybierz pozycję **Zastosuj**.
1. Kliknij przycisk **OK**.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować stronę.

W poniższym przykładzie moduł skonseratora witryny został dodany do gniazda **Selektor witryny** modułu nagłówka zawartego w fragmencie nagłówka o nazwie **HeaderContainer**.

![Przykład modułu selektora witryn we fragmencie nagłówka.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł nagłówka](author-header-module.md)

[Moduł szlaków nawigacyjnych](add-breadcrumb.md)

[Moduł menu nawigacji](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
