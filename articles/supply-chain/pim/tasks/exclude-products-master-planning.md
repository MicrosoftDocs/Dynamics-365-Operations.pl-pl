---
title: Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego
description: Ta procedura dotyczy tworzenia nowego cyklu życia produktu który wyklucza produkty z planowania głównego i obliczeń na poziomie BOM.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 156972cdbf4ffb02b01b00972cc83d003d941378
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567752"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura dotyczy tworzenia nowego cyklu życia produktu który wyklucza produkty z planowania głównego i obliczeń na poziomie BOM.


## <a name="create-an-obsolete-state"></a>Tworzenie stanu przestarzałego
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Ustawienia > Stan cyklu życia produktu.
2. Kliknij przycisk Nowy.
3. W polu Stan wpisz wartość.
4. W polu Jest aktywna dla planowania zaznacz opcję Nie.
5. Wypełnij pole Opis.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Kojarzenie stanu przestarzałego ze zwolnionym produktem
1. Zamknij stronę.
2. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
3. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Wyszukaj nazwę, wprowadzając wartość „M00”.
4. Kliknij przycisk Edytuj.
5. Na liście oznacz wybrany wiersz.
6. W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.

