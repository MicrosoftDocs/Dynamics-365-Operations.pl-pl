---
title: Przełączanie się między projektami dostawcy
description: W tym temacie opisano sposób przełączania integracji danych dostawcy między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902732"
---
# <a name="switch-between-vendor-designs"></a>Przełączanie się między projektami dostawcy

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a>Przepływ danych dostawcy 

Jeśli chcesz użyć innej aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz wyodrębnić informacje o kliencie, możesz skorzystać z podstawowego schematu dostawcy.  

![Podstawowy przepływ dostawcy](media/dual-write-vendor-data-flow.png)
 
Jeśli chcesz użyć innych aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz dalej korzystać z encji **Konto** do przechowywania informacji o dostawcy, możesz skorzystać z nowego rozszerzonego schematu dostawcy. W tym projekcie rozszerzone informacje o dostawcach, takie jak stan wstrzymania dostawcy i profil dostawcy, są przechowywane w jednostce **dostawcy** w Common Data Service. 

![Rozszerzony przepływ dostawcy](media/dual-write-vendor-detail.jpg)
 
Aby użyć rozszerzonego projektu dostawcy, należy wykonać poniższe kroki: 
 
1. Pakiet rozwiązania **SupplyChainCommon** zawiera szablony procesów przepływu pracy przedstawione w poniższym obrazie.
    > [!div class="mx-imgBorder"]
    > ![Szablony procesu przepływu pracy](media/dual-write-switch-3.png)
2. Tworzenie nowych procesów przepływu pracy przy użyciu szablonów procesu przepływu pracy: 
    1. Utwórz nowy proces przepływu pracy dla jednostki **dostawcy**, używając szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce kont** i kliknij przycisk **OK**. Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **konta**.
        > [!div class="mx-imgBorder"]
        > ![Utwórz dostawców w jednostce konta](media/dual-write-switch-4.png)
    2. Utwórz nowy proces przepływu pracy dla jednostki **dostawcy**, używając szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce kont** i kliknij przycisk **OK**. Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **konta**. 
        > [!div class="mx-imgBorder"]
        > ![Aktualizacja jednostki kont](media/dual-write-switch-5.png)
    3. Umożliwia tworzenie nowych procesów przepływu pracy na podstawie szablonów utworzonych w jednostce **konta**. 
        > [!div class="mx-imgBorder"]
        > ![Utwórz dostawców w jednostce dostawców](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Aktualizuj jednostkę dostawcy](media/dual-write-switch-7.png)
    4. Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika. 
        > [!div class="mx-imgBorder"]
        > ![Konwertuj na przepływ pracy w tle](media/dual-write-switch-8.png)
    5. Aktywuj przepływy pracy utworzone w jednostkach **konta** i **dostawcy** w celu rozpoczęcia używania jednostki **Konto** do przechowywania informacji o dostawcy. 
 
