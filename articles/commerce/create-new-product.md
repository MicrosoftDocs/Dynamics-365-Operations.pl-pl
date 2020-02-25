---
title: Tworzenie nowego produktu
description: W tym temacie opisano, jak dodać utworzyć nowy produkt w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 356bf91b2a946e7c0f5d5af9e2fe0b64342b856e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001974"
---
# <a name="create-a-new-product"></a>Tworzenie nowego produktu


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać utworzyć nowy produkt w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Produkt jest definiowany głównie przez numer produktu, nazwę i opis. Są jednak potrzebne również inne dane, aby odpowiednio opisać produkt lub usługę:

## <a name="create-a-new-product"></a>Tworzenie nowego produktu

1. W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Produkty i kategorie \> Produkty według kategorii**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Z listy rozwijanej **Typ produktu** wybierz opcję **Towar** lub **Usługa**.
1. Z listy rozwijanej **Podtyp produktu** wybierz **Produkt** (jeśli produkt nie będzie miał wariantów) lub **Produkt główny** (jeśli produkt będzie miał warianty).
1. W polu **numer produktu** wprowadź numer produktu, jeśli nie został on jeszcze wstępnie wypełniony.
1. W polu **Nazwa produktu** wprowadź nazwę produktu.
1. W polu **Nazwa wyszukiwania** wprowadź nazwę wyszukiwaną.
1. Z listy rozwijanej **Kategoria sieci sprzedaży** wybierz odpowiednią kategorię.
1. Jeśli produkt jest zestawem, wybierz **Tak** dla **Zestawu produktów**.
1. Jeśli podtyp produktu jest produktem głównym, należy skonfigurować **grupę wymiarów produktu** w taki sposób, aby obejmowała ona obsługiwane warianty. Wybierz **kolor**, **rozmiar**, **styl** i **konfigurację**. W razie potrzeby może być konieczne utworzenie dodatkowych grup wymiarów produktów.
1. Z listy rozwijanej **Technologia konfiguracji** wybierz odpowiednią opcję.
1. Kliknij przycisk **OK**.

Poniższy obraz przedstawia przykład dodawanego produktu.

![Tworzenie produktu](media/create-new-product.png)

Po dodaniu produktu można dla niego określić dodatkowe dane, takie jak **opis produktu**, **grupy wariantów**, **grupy wymiarów**, **atrybuty produktów** i **produkty pokrewne**.

Poniższy obraz przedstawia dodatkowe szczegóły produktu.

![Szczegóły produktu](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Utwórz warianty produktu

Jeśli podtyp produktu to **produkt główny**, konieczne będzie utworzenie konkretnych wariantów. 

Aby utworzyć warianty produktu, wykonaj następujące kroki.

1. W okienku akcji wybierz pozycję **Warianty produktu**.
1. Jeśli w okienku akcji wybrano grupy wariantów, wybierz **Sugestie wariantów*.
1. Wybierz warianty, które chcesz obsługiwać dla produktu.
1. Wybierz opcję **Utwórz**.

## <a name="release-a-product"></a>Zwolnienie produktu

Aby sprzedać produkt, należy go najpierw zwolnić do firmy.

1. Na stronie produkt wybierz pozycję **Zwolnione produkty**.

    ![Zwolniony produkt](media/create-new-product-3.png)

1. Wybierz produkt, który ma zostać zwolniony, a następnie wybierz przycisk **Dalej**.

    ![Wybierz produkt do zwolnienia](media/create-new-product-4.png)

1. Wybierz zestaw wariantów produktu, który ma zostać zwolniony, a następnie wybierz przycisk **Dalej**.

    ![Wybierz warianty do zwolnienia](media/create-new-product-5.png)

1. Wybierz firmę i wybierz przycisk **Dalej**.

    ![Wybierz firmę](media/create-new-product-6.png)

1. Wybierz **Zakończ**.

    ![Zakończ zwolnienie produktu](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Konfiguruj zwolniony produkt

Po zwolnieniu produkt będzie wymagał dodatkowej konfiguracji, która obejmuje dodanie ceny do produktu.

1. W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Zwolnione produkty według kategorii**.
1. Wybierz węzeł kategorii produktów dla produktu, który został zwolniony, a następnie wybierz produkt z listy produktów.
1. Na okienku akcji wybierz opcję **Edytuj**.
1. W sekcji **zakup** skonfiguruj wymagane właściwości, takie jak **jednostka**, **cena** i **ilość**.
1. W okienku akcji wybierz opcję **Sprawdzanie poprawności**, aby upewnić się, że nie zgłoszono błędów dla brakujących pól.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład konfiguracji dla zwolnionego produktu..

![Konfiguruj zwolniony produkt](media/create-new-product-8.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie firm](channels-legal-entities.md)

[Utwórz grupę wariantów](create-variant-group.md) 
