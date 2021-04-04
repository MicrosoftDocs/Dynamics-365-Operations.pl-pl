---
title: Dodawanie kodu HTML do wiadomości e-mail transakcyjnych i wiadomości e-mail o przychodach
description: W tym temacie opisano sposób wstawiania kodów PIN i kodów kreskowych reprezentujących identyfikatory zamówień do wiadomości e-mail o transakcjach i przyjęciach Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 3cc4fcb1237f8409a89b3d4818c132c60c57b5a0
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555429"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>Dodawanie kodu HTML do wiadomości e-mail transakcyjnych i wiadomości e-mail o przychodach

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób wstawiania kodów PIN i kodów kreskowych reprezentujących identyfikatory zamówień do wiadomości e-mail o transakcjach i przyjęciach Microsoft Dynamics 365 Commerce.

Możesz łatwo dołączyć kody QR i kody kreskowe do e-maili transakcyjnych, aby przyspieszyć proces wyszukiwania zamówień w środowisku sprzedaży detalicznej. Aby wstawić kody QR i kody kreskowe do wiadomości e-mail, użyj tagu HTML **\<img\>**, który żąda kodu QR lub obrazu kodu kreskowego z usługi generowania i renderowania. Firma Microsoft nie dostarcza tej usługi. Istnieje jednak wiele bezpłatnych lub niedrogich usług, które mogą obsługiwać kody QR lub kody kreskowe generowane dynamicznie na podstawie wartości przekazywanej w ciągu zapytania.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>Dodaj kod QR lub kod kreskowy do e-maila transakcyjnego

Aby wstawić kod QR lub kod kreskowy do e-maila transakcyjnego, który jest wysyłany w ramach zakupu w handlu elektronicznym, wykonaj następujące kroki.

1. Otwórz źródłowy kod HTML szablonu transakcyjnej wiadomości e-mail i dodaj tag HTML **\<img\>** wskazujący na Twój kod QR lub usługę kodów kreskowych. Oto przykład.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    Oto wyjaśnienie poprzedniego przykładu:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** reprezentuje domenę Twojego kodu QR lub usługi kodów kreskowych.
    - **dane** reprezentuje parametr używany przez usługę kodu QR lub kodu kreskowego do odbierania treści, która powinna być renderowana jako kod QR lub kod kreskowy.

        Wartość **%salesid%** musi być przypisana do tego parametru. W tym przykładzie należy zauważyć, że wartość jest również używana jako tekst alternatywny dla obrazu.

    - Parametry **param1** i **param2** reprezentują dodatkowe parametry opcjonalne.

1. Przejdź do **Retail i Commerce \> Konfiguracja Headquarters \> Parametry \> Organizacja szablonów wiadomości e-mail**, a następnie przekaż zaktualizowany kod HTML do odpowiedniego transakcyjnego szablonu wiadomości e-mail.

> [!NOTE]
> Parametry mogą się różnić między dostawcami usług kodów QR i kodów kreskowych. Dlatego należy skontaktować się z dostawcą usług w celu potwierdzenia parametrów, do których należy przypisać wartości.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>Dodaj kod QR lub kod kreskowy do e-maila odbioru 

Aby wstawić kod QR lub kod kreskowy do wiadomości e-mail z potwierdzeniem, którą można wysłać po dokonaniu zakupu w punkcie sprzedaży (POS), wykonaj następujące kroki.

1. Otwórz źródłowy kod HTML szablonu odbioru wiadomości e-mail i dodaj tag HTML **\<img\>** wskazujący na Twój kod QR lub usługę kodów kreskowych. Oto przykład:

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    Oto wyjaśnienie poprzedniego przykładu:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** reprezentuje domenę Twojego kodu QR lub usługi kodów kreskowych.
    - **dane** reprezentuje parametr używany przez usługę kodu QR lub kodu kreskowego do odbierania treści, która powinna być renderowana jako kod QR lub kod kreskowy.

        Wartość **%receiptid%** musi być przypisana do tego parametru. W tym przykładzie należy zauważyć, że wartość jest również używana jako tekst alternatywny dla obrazu.

    - Parametry **param1** i **param2** reprezentują dodatkowe parametry opcjonalne.

1. Przejdź do **Retail i Commerce \> Konfiguracja Headquarters \> Parametry \> Organizacja szablonów wiadomości e-mail**, a następnie przekaż zaktualizowany kod HTML do odpowiedniego szablonu, który ma identyfikator wiadomości e-mail **emailrecpt**.

> [!NOTE]
> Parametry mogą się różnić między dostawcami usług kodów QR i kodów kreskowych. Dlatego należy skontaktować się z dostawcą usług w celu potwierdzenia parametrów, do których należy przypisać wartości.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wysyłanie paragonów pocztą e-mail z aplikacji Modern POS (MPOS)](email-receipts.md)

[Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych](email-templates-transactions.md)
