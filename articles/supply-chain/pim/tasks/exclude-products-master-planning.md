---
title: Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego
description: Ta procedura dotyczy tworzenia nowego cyklu życia produktu który wyklucza produkty z planowania głównego i obliczeń na poziomie BOM.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cadf1d812e737309dbe8ca26d04ffb1ee88ef16a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818044"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]