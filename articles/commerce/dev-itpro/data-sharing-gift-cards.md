---
title: Udostępnianie danych między firmami dla kart upominkowych
description: W tym artykule opisano sposób konfigurowania Microsoft Dynamics 365 Commerce do używania funkcji udostępniania danych usługi Dynamics 365 Finance w różnych obszarach danych do synchronizacji danych kart upominkowych.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: bc0df6c4aac72907e8523069e3f1ae100780dc3c
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473939"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Udostępnianie danych między firmami dla kart upominkowych

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania rozwiązania Microsoft Dynamics 365 Commerce tak, by używało udostępniania danych usługi Dynamics 365 Finance do synchronizacji danych kart upominkowych. Funkcja udostępniania rekordów danych może następnie służyć do udostępniania danych między firmami między dwoma obszarami danych. W ten sposób wewnętrzna tabela upominkowa rozwiązania Commerce może udostępniać dane między firmami. Aby uzyskać więcej informacji dotyczących udostępniania danych między firmami w programie Dynamics 365 Finance, zobacz temat [Udostępnianie danych między firmami](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Firma | Firma w środowisku usługi Dynamics 365 Finance. |
| Karta upominkowa | Produkt wewnętrznej karty upominkowej rozwiązania Dynamics 365 Commerce. |

## <a name="prerequisites"></a>Wymagania wstępne

Użytkownicy muszą skonfigurować swoje środowisko do udostępniania danych między firmami, jak opisano w temacie [Udostępnianie danych między firmami](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

Tabela **RetailGiftCardTable** musi mieć w polu **DataSharingType** wartość **Duplikat**, aby umożliwić udostępnianie zduplikowanych rekordów (DRS) dla tabeli kart upominkowych. Aby uzyskać więcej informacji, zobacz temat [Udostępnianie danych między firmami dla deweloperów](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Konfiguruj udostępnianie danych między firmami dla kart upominkowych

Aby skonfigurować udostępnianie danych między firmami dla kart upominkowych, wykonaj te kroki.

1. W centrali Commerce headquarters przejdć do **Administracja systemu \> Ustawienia \> Konfiguruj udostępnianie danych między firmami**.
1. W okienku akcji wybierz **Nowe**, aby dodać rekord udostępniania danych.
1. W polu **Nazwa** wprowadź nazwę rekordu udostępniania danych (na przykład **Karty upominkowe**).
1. W sekcji **Tabele i pola do udostępnienia** wybierz pozycję **Dodaj**.
1. W oknie dialogowym **Udostępnij nową tabelę** w polu **Nazwa tabeli** wprowadź tabelę **RETAILGIFTCARDTABLE** (tabelę dla detalicznych kart upominkowych). W polu **Etykieta tabeli** powinna być automatycznie ustawiona **Tabela kart upominkowych**.
1. Upewnij się, że są zaznaczone wszystkie pola wyboru **Zapisz dane według firm**, **Ma unikatowy indeks** i **Jeszcze nie udostępnione**. Zaznaczenie tych pól wyboru wyzwala weryfikację związaną z funkcjami udostępniania danych.
1. Wybierz opcję **Dodaj tabelę**. Rekord **tabela kart upominkowych (RetailGiftCardTable)** powinien teraz być widoczny w **Tabelach i polach do udostępnienia**. Aby wyświetlić wszystkie pola tabeli automatycznie skojarzone z tabelą, należy wybrać symbol daszka (^).
1. W sekcji **Firmy, które współużytwają rekordy w tych tabelach**, wybierz opcję **Dodaj**, aby dodać firmę, której mają być udostępnione dane.
1. W wierszu w obszarze **Firma** wybierz firmę z listy rozwijanej.
1. W polu **Nazwa** wpisz nazwę firmy.
1. Powtórz kroki od 8 do 10, aby dodać więcej wierszy firm.
1. Po dodaniu wierszy firmy w okienku akcji wybierz opcję **Włącz**.
1. Zostanie wyświetlony komunikat ostrzegawczy z komunikatem: „Zalecane jest wykonywanie tej akcji tylko w godzinach innych niż godziny pracy. Wszelkie operacje równoczesnych transakcji nie powiodą się dla tabel w zasadach. Czy chcesz kontynuować?” Wybierz przycisk **Tak**, aby wyrazić zgodę.
1. Otrzymasz komunikat ostrzegawczy o treści: „Czy chcesz teraz skopiować wszystkie istniejące dane do wszystkich udostępnionych firm?” Wybierz przycisk **Tak**, aby wyrazić zgodę.

Po wyrażeniu zgody na oba komunikaty tabele rozpoczną kopiowanie danych między skonfigurowanymi firmami. Salda karty upominkowej jednej firmy będą wtedy widoczne dla drugiej firmy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Płatności — często zadawane pytania](payments-retail.md)

[Moduł realizacji transakcji](../add-checkout-module.md)

[Moduł płatności](../payment-module.md)
