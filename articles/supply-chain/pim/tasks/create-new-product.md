---
title: Tworzenie nowego produktu
description: W tym temacie opisano sposób tworzenia nowego udostępnionego produktu.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a4745fe4fc44f85bcfd388ee573f5a6d0cd8519
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435224"
---
# <a name="create-a-new-product"></a>Tworzenie nowego produktu

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia nowego udostępnionego produktu. Zwykle robi to projektant produktów. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-product"></a>Tworzenie produktu
1. W okienku nawigacji przejdź do opcji **Moduły > Zarządzanie informacjami o produktach > Produkty > Produkty**.
2. Wybierz pozycję **Nowy**.
3. W polu **Numer produktu** wpisz wartość. Jeśli dla numeru produktu nie skonfigurowano sekwencji identyfikatorów, należy ją wprowadzić ręcznie.  
4. W polu **Nazwa produktu** wpisz wartość. Nazwa produktu jest domyślnie aliasem. W razie potrzeby można to zmienić.  
5. Kliknij przycisk **OK**.

## <a name="set-up-dimension-groups"></a>Konfigurowanie grup wymiarów
1. Wybierz **Grupy wymiarów**, aby otworzyć rozwijane okno dialogowe.
2. W polu **Grupa wymiaru magazynowania** wpisz lub wprowadź wartość. Grupa wymiarów magazynowania określa, które wymiary magazynowania należy wprowadzić w każdej transakcji produktu i jak będą one śledzone w zapasach.  
3. W polu **Grupa wymiaru śledzenia** wpisz lub wprowadź wartość. Grupa wymiarów śledzenia określa, które wymiary śledzenia należy wprowadzić dla każdej transakcji produktu i jak będą one obsługiwane w zapasach.  
4. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]