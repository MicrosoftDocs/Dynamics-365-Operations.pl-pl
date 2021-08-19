---
title: Poprawianie informacji o śledzeniu zapasów
description: Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów.
author: MarkusFogelberg
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aae70bf74f3b640167a01d8a5935989d7225695dc5d4f3817ac2ce92d191cb31
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766710"
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