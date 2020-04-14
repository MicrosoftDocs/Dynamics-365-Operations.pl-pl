---
title: Sprawdzanie jakości towarów
description: W tym temacie wyjaśniono sposób przetwarzania zlecenia kontroli jakości.
author: perlynne
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 75fbfbb7b993b528e96d247dafa2bdfe20837987
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145624"
---
# <a name="inspect-the-quality-of-goods"></a>Sprawdzanie jakości towarów

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono sposób przetwarzania zlecenia kontroli jakości. Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Przed rozpoczęciem tej przykładowej procedury należy potwierdzić zamówienia zakupu „000016” i zaksięgować dokument przyjęcia produktu. Spowoduje to automatyczne utworzenie zlecenia kontroli jakości. Kontrole jakości są zazwyczaj wykonywane przez pracownika ds. kontroli jakości.


## <a name="select-a-quality-order"></a>Wybieranie zlecenia kontroli jakości
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Zadania okresowe > Zarządzanie jakością > Zlecenia kontroli jakości**.
2. Przed rozpoczęciem tej procedury wybierz utworzone zlecenie kontroli jakości.  

## <a name="record-test-results"></a>Rejestrowanie wyników testów
1. Wybierz opcję **Wyniki**.
2. Wybierz opcję **Edycja**.
3. W polu **Liczba wyników** wprowadź liczbę.
4. W polu **Wynik** wybierz odpowiedni rekord z menu rozwijanego.  
- W tym przykładzie wynik bazuje na wstępnie zdefiniowanym wyniku. Zwyczajowo rejestruje się bardziej szczegółowy wynik inspekcji, na przykład rozmiaru lub innego wymiaru.  
5. Wybierz opcję **Zapisz**.
6. Zamknij stronę.

## <a name="validate-the-quality-order"></a>Sprawdź poprawność zlecenia kontroli jakości
1. Wybierz **Potwierdź**.
2. W polu **Poprawność sprawdzona przez** wybierz użytkownika wykonującego inspekcję z menu rozwijanego.  
3. Kliknij opcję **Wybierz**.
4. Kliknij przycisk **OK**.
5. Zamknij stronę.

