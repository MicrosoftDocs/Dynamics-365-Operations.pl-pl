---
title: Definiowanie modeli przepływu produkcji
description: Modele przepływu produkcji opisują sposób obliczania i obsługi zdolności produkcyjnych komórek roboczych w produkcji oszczędnej.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e410928bc850e1f3427c9536e9943d1196be7a05
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "336734"
---
# <a name="define-production-flow-models"></a>Definiowanie modeli przepływu produkcji

[!include [task guide banner](../../includes/task-guide-banner.md)]

Modele przepływu produkcji opisują sposób obliczania i obsługi zdolności produkcyjnych komórek roboczych w produkcji oszczędnej. Dlatego zdefiniowanie modelu przepływu produkcji jest warunkiem wstępnym zdefiniowania komórek roboczych. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="define-a-production-flow-model"></a>Definiowanie model przepływu produkcji 
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Modele przepływu produkcji.
2. Kliknij przycisk Nowy.
3. W polu Model przepływu produkcji wprowadź identyfikator modelu przepływu produkcji.
4. W polu Typ modelu wybierz opcję.
    * Istnieją dwa typy modeli: Produktywność i Godziny. W typie Produktywność zdolności produkcyjne komórek roboczych korzystających z tego modelu przepływu produkcji będą wyrażane i obliczane w ilościach produktów. W typie Godziny zdolności produkcyjne komórek roboczych korzystających z tego modelu przepływu produkcji będą wyrażane i obliczane w godzinach. Należy zauważyć, że nie można zmienić tej właściwości dla istniejącego modelu przepływu produkcji. Po zarezerwowaniu zdolności produkcyjnych komórki roboczej nie można zmienić typu modelu przepływu produkcji.  
5. W polu Cykl EPE wprowadź liczbę dni.
    * Interwał opisuje okres, w którym każda część wytwarzana w przepływie produkcji lub komórce roboczej zostanie wykonana co najmniej raz. Im krótszy cykl EPE, tym bardziej elastyczny proces produkcji. Jeśli cykl EPE = 0, produkty dla całego popytu mogą zostać wytworzone w tym samym dniu. Cykl EPE jest używany do planowanie zadań produkcji oszczędnej. Przy planowaniu zadania w komórce roboczej o cyklu EPE = 5 proces planowania sprawdza zdolności produkcyjne komórki roboczej na dzień Data wymagalności - cykl EPE (5 dni przed datą wymagalności), aby mieć pewność, że produkt może zostać wyprodukowany w tym cyklu. Czas realizacji zapasów produktu jest zazwyczaj równy lub dłuższy niż cykl EPE powiązanego procesu produkcji.  
6. W polu Typ okresu planowania wybierz opcję.
    * Po zarezerwowaniu zdolności produkcyjnych komórki roboczej nie można zmienić typu okresu planowania. Dla danej komórki roboczej można wybierać tylko modele przepływu produkcji o tym samym typie okresu.  
7. W polu Horyzont czasowy planowania wpisz liczbę.
    * Horyzont czasowy planowania opisuje liczbę dni, kiedy można tworzyć rezerwacje zdolności produkcyjnych dla powiązanych komórek roboczych. W polu Horyzont czasowy planowania wpisz liczbę dni.   Zadania przetwarzania w systemie Kanban, które wykraczają poza ten okres, nie będą planowano przy użyciu planowania automatycznego. Horyzont jest zazwyczaj dwa razy dłuższy niż średni czas realizacji zapasów dla produktów wytwarzanych w przepływie produkcji lub komórce roboczej. Cykl EPE nie powinien być dłuższy niż połowa horyzontu czasowego planowania.     
8. W polu Reakcja na niedobór zdolności produkcyjnych wybierz opcję.
    * Opóźnij — Odroczenie pełnego popytu w zdarzeniu planowania do następnego dostępnego dnia produkcji mającego dostępną produktywność. Anuluj — Zakończenie automatycznego planowania w zdarzeniu planowania i pozostawienie powiązanych zadań niezaplanowanych.   Dodaj do żądanego dnia — Planowanie żądanych zadań na żądany okres. Powoduje to przeciążenie komórki w danym dniu i wymaga od planisty przeglądu i ręcznej interakcji.   Dystrybucja do dostępnych okresów — Rozdział różnych zadań zdarzenia planowania między wszystkie dostępne produkcji dni, począwszy od pierwszego dostępnego dnia. Minimalną ilością do rozdziału jest ilość z zadania w systemie Kanban. Dystrybucja powoduje przypisanie minimalnej ilości planowania (ilości z kart Kanban) do każdego dnia o wystarczającej dostępnej produktywności.  

