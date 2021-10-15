---
title: Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego
description: Ta procedura dotyczy tworzenia nowego cyklu życia produktu który wyklucza produkty z planowania głównego i obliczeń na poziomie BOM.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f72be341b81515b7c5540d66f61647df93af41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567038"
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