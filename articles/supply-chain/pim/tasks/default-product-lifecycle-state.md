--- 
title: "Tworzenie domyślnego stanu cyklu życia produktu"
description: "W tej procedurze pokazano, jak utworzyć domyślny stan cyklu życia produktu, a także jak skojarzyć stan domyślny ze zwolnionymi produktami."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: 06a6c7c8fa767edf6fdf50c3c971b6d767f8755f
ms.contentlocale: pl-pl
ms.lasthandoff: 02/08/2018

---
# <a name="create-a-default-product-lifecycle-state"></a>Tworzenie domyślnego stanu cyklu życia produktu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć domyślny stan cyklu życia produktu, a także jak skojarzyć stan domyślny ze zwolnionymi produktami.


## <a name="create-a-default-lifecycle-state"></a>Tworzenie domyślnego stanu cyklu życia
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Ustawienia > Stan cyklu życia produktu.
2. Kliknij przycisk Nowy.
3. W polu Stan wpisz wartość.
4. Wybierz opcję Tak w ustawieniu Domyślny po zwolnieniu do pola firmy.
5. Wypełnij pole Opis.
6. W polu Jest aktywna dla planowania zaznacz opcję Nie.

> [!NOTE]
> Jeśli nowy zwolniony produkt nie powinien być uwzględniony w planowaniu głównym, wybierz opcję Nie. Jeśli planowanie główne powinno być uwzględnione, należy pozostawić dla formantu wartość domyślną Tak.  

## <a name="create-a-new-released-product"></a>Tworzenie nowego zwolnionego produktu
1. Zamknij stronę.
2. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
3. Kliknij przycisk Nowy.
4. W polu Numer produktu wpisz wartość.
5. W polu Nazwa produktu wpisz wartość.
6. W polu Alias wpisz wartość.
7. W polu grupa modelu produktu wpisz lub wprowadź wartość.
8. W polu Grupa towarów wprowadź lub wybierz wartość.
9. W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.
10. W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.
11. Kliknij przycisk OK.

> [!NOTE]
> Domyślny stan cyklu życia produktu to definicja globalna.  

## <a name="change-the-product-to-an-active-state"></a>Zmiana stanu produktu na aktywny
1. W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.

> [!NOTE]
> Załóżmy, że skonfigurowano stan aktywny. W takim przypadku można wybrać aktywny, aby zezwolić na użycie produktu w planowaniu głównym o obliczaniu na poziomie BOM. Oczywiście ma to sens tylko wówczas, gdy określono wszystkie dane szczegółowe produkty wymagane do spójnego planowania.  


