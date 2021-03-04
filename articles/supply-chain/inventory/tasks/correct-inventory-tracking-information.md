---
title: Poprawianie informacji o śledzeniu zapasów
description: Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8a488d4c30923445b3ebc2626a79b8fa45012c7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435491"
---
# <a name="correct-inventory-tracking-information"></a>Poprawianie informacji o śledzeniu zapasów

[!include [banner](../../includes/banner.md)]

Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów. W tym przykładzie zaktualizujemy informacje o towarze wchodzącym skład partii, zmieniając niepoprawnie zarejestrowaną partię na inną partię. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USPI lub własnych danych. W przypadku korzystania z własnych danych musi istnieć towar, który może wchodzić w skład partii, ale nie jest kontrolowany przez lokalizację. Trzeba mieć również skonfigurowany arkusz zapasów dla przeniesień zapasów. Te zadania zazwyczaj wykonuje pracownik magazynu.


## <a name="create-an-inventory-transfer-journal"></a>Tworzenie arkusza przeniesienia zapasów
1. Przejdź do okna Przeniesienie.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wprowadź lub wybierz wartość.
4. Kliknij przycisk OK.

## <a name="create-journal-lines"></a>Tworzenie wierszy arkusza
1. Kliknij przycisk Nowy.
2. W polu Numer towaru wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USPI, wybierz opcję M5003.  
3. Wprowadź liczbę w polu Ilość.
4. Kliknij kartę Wymiary magazynowe.
5. W polu Numer partii wprowadź lub wybierz wartość.
6. W polu Oddział wprowadź lub wybierz wartość.
7. W polu Magazyn wprowadź lub wybierz wartość.
8. W polu Numer partii wprowadź lub wybierz wartość.

## <a name="post-the-journal"></a>Księguj arkusz
1. Kliknij przycisk Księguj.
2. Kliknij przycisk OK.

## <a name="check-tracing-information"></a>Sprawdzanie informacji o śledzeniu
1. Kliknij opcję Zapasy.
2. Kliknij przycisk Śledzenie.
3. Kliknij przycisk OK.
    * Przy użyciu tych informacji śledzenia można prześledzić wstecz, z której partii dokonano korekty zapasów.  Wyświetlanie tych informacji umożliwia także strona Śledzenie towaru.  
4. Zamknij stronę.

## <a name="check-inventory-transactions"></a>Sprawdzanie transakcji magazynowych
1. Kliknij opcję Zapasy.
2. Kliknij opcję Transakcje.
    * W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]