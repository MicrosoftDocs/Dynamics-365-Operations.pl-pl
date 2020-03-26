---
title: Ustawianie magazynu
description: W tym temacie opisano sposób konfigurowania magazynu, który ma być używany z nowym kanałem w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 6da72ae612f0520965a2b11a21123d4642303ac3
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113766"
---
# <a name="warehouse-set-up"></a>Ustawianie magazynu


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania magazynu, który ma być używany z nowym kanałem w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Każdy kanał Commerce wymaga, aby skonfigurowany magazyn był skojarzony z nim. Poniższe procedury zapewniają minimalną konfigurację wymaganą do skonfigurowania magazynu dla kanału Commerce. Aby uzyskać więcej informacji dotyczących konfiguracji magazynu, zobacz [Omówienie zarządzania magazynem](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).

## <a name="configure-a-warehouse-site"></a>Konfiguracja oddział magazynu

Przed skonfigurowaniem magazynu należy skonfigurować oddział magazynu.

Aby skonfigurować oddział magazynu, wykonaj następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Oddziały**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wprowadź wartość w polu **Oddział**.
1. Wprowadź wartość w polu **Nazwa**.
1. W sekcji **Ogólne** określ odpowiednią **Strefę czasową**.
1. W polu **Adresy** wprowadź adres.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład oddział magazynu.

![Przykład oddziału magazynu](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Ustawianie magazynu

Aby skonfigurować magazyn, należy wykonać następujące czynności.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wprowadź lub wybierz wartość w polu **Magazyny**.  Jeśli jest to mapowanie 1:1 do sklepu, należy rozważyć użycie nazwy sklepu lub nazwy regionalnego centrum dystrybucji.
1. Wprowadź wartość w polu **Nazwa**.
1. Z listy rozwijanej **oddziału** Wybierz utworzoną wcześniej witrynę magazynową.
1. W polu **Typ** zaznacz opcję **Domyślny**.
    - Aby utworzyć **Magazyn kwarantanny**, najpierw trzeba wykonać poniższe kroki w celu utworzenia dodatkowego magazynu, w którym ustawiono **Typ** jako **Kwarantanna**.
    - Aby utworzyć **Magazyn tranzytowy**, najpierw trzeba wykonać poniższe kroki w celu utworzenia dodatkowego magazynu, w którym ustawiono **Typ** jako **Tranzyt**.
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="set-up-inventory-aisles"></a>Ustawianie korytarzy w magazynie

Aby skonfigurować korytarzy magazynowych, należy wykonać następujące czynności.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Ustawienia lokalizacji \> Korytarze w magazynie**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Z listy rozwijanej **Magazyn** Wybierz utworzoną wcześniej witrynę magazynową.
1. W polu **Korytarz** wprowadź nazwę (na przykład „Def”).
1. W polu **Nazwa** wprowadź nazwę (na przykład „Domyślny korytarz”).
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="set-up-warehouse-inventory-locations"></a>Ustaw lokalizacje zapasów

Aby skonfigurować lokalizacje magazynów magazynowych dla standardowych, uszkodzonych i zwróconych zapasów, należy wykonać następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.
1. Zaznacz utworzony wcześniej magazyn.
1. Na okienku akcji wybierz opcję **Edytuj**.
1. W okienku akcji wybierz opcję **Magazyn**, a następnie wybierz opcję **Lokalizacja zapasów**.
1. W okienku akcji wybierz opcję **Nowy**. Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.
    1. W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej. 
    1. Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**
    1. W polu **Lokalizacja** wprowadź nazwę magazynu.
    1. Na okienku akcji wybierz opcję **Zapisz**.
 1. W okienku akcji wybierz opcję **Nowy**.  Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.
    1. W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.  
    1. Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**
    1. W polu **Lokalizacja** wprowadź „uszkodzony”.
    1. Na okienku akcji wybierz opcję **Zapisz**.
 1. W okienku akcji wybierz opcję **Nowy**.  Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.
    1. W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej. 
    1. Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**
    1. W polu **Lokalizacja** wprowadź „Zwrócony”.
    1. Na okienku akcji wybierz opcję **Zapisz**.
    
Na poniższym rysunku przedstawiono konfigurację lokalizacji magazynu w San Francisco.

![Przykładowe ustawienia lokalizacji zapasów](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Zakończ konfigurację magazynu

Aby zakończyć tę konfigurację magazynu, należy wykonać następujące czynności.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.
1. Zaznacz utworzony wcześniej magazyn.
1. Na okienku akcji wybierz opcję **Edytuj**.
1. W **Zarządzanie zapasami i magazynem**:
    1. Ustaw **Domyślna lokalizacja przychodu** jako lokalizację domyślną utworzoną powyżej.
    1. Wybierz **Domyślna lokalizacja rozchodu** jako lokalizację domyślną utworzoną powyżej.
1. W sekcji **Adresy** wprowadź adres magazynu.
1. W sekcji **Retail**: 
    1. W polu **Domyślna lokalizacja zwrotu** wprowadź pozostałą lokalizację zwrotu utworzoną wcześniej.
    1. Określ wartość **Sklep** na **Tak**.
    1. W polu **Waga** ustaw wartość **1.00**. 
    1. W polu **Wymiary magazynowania** wprowadź dkomyślną lokalizację utworzoną wcześniej.
1. W sekcji **Magazyn** ustaw **Ujemne wartości magazynu fizycznego** na wartość **Tak**.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia szczegóły dotyczące skonfigurowanego magazynu.

![Przykładowy magazyn skonfigurowany](media/warehouse-sample.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania magazynem](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Konfigurowanie kanału sprzedaży](channel-setup-retail.md)
    
[Konfigurowanie kanału internetowego](channel-setup-online.md)

[Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)





