---
title: Zastosuj ustawienia dodawania produktu do koszyka
description: W tym temacie omówiono ustawienia opcji "Dodaj produkt do koszyka" i opisano sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c1d29b84d79ab503580478a1553514ddf992ca46
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2021
ms.locfileid: "6637984"
---
# <a name="apply-add-product-to-cart-settings"></a>Zastosuj ustawienia dodawania produktu do koszyka

[!include [banner](includes/banner.md)]

W tym temacie omówiono ustawienia opcji **Dodaj produkt do koszyka** i opisano sposób ich stosowania w Microsoft Dynamics 365 Commerce.

Podczas dodawania produktu do koszyka w witrynie handlu elektronicznego Dynamics 365 Commerce obsługiwane są różne przepływy pracy. Na przykład, użytkownik witryny może zostać przeniesiony na stronę koszyka. Alternatywnie, użytkownik może pozostać na bieżącej stronie, ale otrzyma powiadomienie, które potwierdzi, że produkt został dodany do koszyka.

Aby obsługiwać różne przepływy pracy, pole **Dodaj produkt do koszyka** jest dostępne w **Ustawienia \> Rozszerzenia** w witrynie Commerce. Wybierz jedną z następujących opcji ustawień w celu zaimplementowania odpowiedniego przepływu pracy:

- **Przejdź do strony koszyka** – Kiedy użytkownicy dodają przedmiot do koszyka, są przenoszeni na stronę koszyka.
- **Wyświetl powiadomienie** – Kiedy użytkownicy dodają produkt do koszyka, otrzymują powiadomienie potwierdzające i mogą kontynuować przeglądanie na stronie szczegółów produktu (PDP).
- **Pokaż mini koszyk** — gdy użytkownicy dodają towar do koszyka, jest wyświetlana jego zawartość. Użytkownicy mogą przeglądać wszystkie pozycje w koszyku, a jeśli są gotowi, mogą przejść do kasy.
- **Pokaż powiadomienia za pomocą modułu Powiadomienia** – Gdy użytkownicy dodają towar do koszyka, moduł powiadomień jest używany do pokazywania powiadomienia potwierdzenia. Aby ta opcja ustawienia działała, moduł powiadomień musi zostać dodany do nagłówka strony.
- **Nie przechodź do strony koszyka** – Kiedy użytkownicy dodają przedmiot do koszyka, pozostają na bieżącej stronie.

Na poniższej ilustracji pokazano przykład opcji wyboru **Dodaj produkt do koszyka** w Konstruktorze witryn.

![Przykład dodawania produktu do koszyka w konstruktorze witryn](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - Ustawienia w witrynie **Dodaj produkt do koszyka** są dostępne w wersji Dynamics 365 Commerce 10.0.11. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać informacje na temat aktualizacji pliku appsettings.json, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).
> - Opcja ustawienia **Pokaż mini koszyk** jest dostępna od wersji Dynamics 365 Commerce 10.0.20. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać informacje na temat aktualizacji pliku appsettings.json, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

Na poniższej ilustracji przedstawiono przykład powiadomienia z potwierdzeniem „dodanie do koszyka” w witrynie firmy Fabrikam.

![Przykład powiadomienia o dodaniu do koszyka w witrynie firmy Fabrikam](./media/ecommerce-addtocart-notifications.PNG)

Na poniższej ilustracji przedstawiono przykład powiadomienia z potwierdzeniem „dodanie do koszyka” w witrynie Adventure Works.

![Przykład powiadomienia o dodaniu do koszyka w witrynie firmy Adventure Works](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł wyboru sklepu](store-selector.md)
