--- 
title: "Przenoszenie środka trwałego"
description: "W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b193cf6fbed810f0d5234514573d0f5c23c7b2c8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-a-fixed-asset"></a>Przenoszenie środka trwałego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.  Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.

1. Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.
2. Na liście odszukaj i zaznacz środek trwały, który ma zostać przeniesiony.
3. W okienku akcji kliknij pozycję Środek trwały.
4. Kliknij opcję Przenieś środki trwałe.
5. W polu Data przeniesienia wprowadź datę.
6. Wprowadź komentarze opisujące przeniesienie.
    * Ta lista przedstawia wszystkie księgi dla środka trwałego.  
7. Oznacz księgi, które mają zostać przeniesione do nowego zestawu wymiarów finansowych.
    * Ta lista przedstawia istniejące wartości wymiarów finansowych dla wybranej księgi.  
    * Zaznacz wymiar finansowy, który chcesz zaktualizować dla wybranej księgi środków trwałych.  
8. W polu Wymiar finansowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Ustaw wartości odpowiednich innych wymiarów finansowych.  
    * Po przeniesieniu zmieniają się wszystkie wartości wymiarów finansowych, niezależnie od tego, czy wartość została wprowadzona czy też pole było puste. Na przykład mogła być wprowadzono wartość wymiaru Jednostka biznesowa, a niewypełnione wymiary Centrum kosztów i Dział. Jeśli struktura konta pozwala na puste wartości wymiarów Centrum kosztu i Dział, przeniesienie spowoduje, że każdy model ewidencji otrzyma nową wartość wymiaru Jednostka biznesowa, a puste wartości wymiarów Centrum kosztów i Dział.  
9. Kliknij przycisk Aktualizuj.
    * Przed sfinalizowaniem przeniesienia masz możliwość podglądu efektów zmian.  
    * Przejrzyj wyniki przed przeniesieniem ksiąg środków trwałych.  
10. Kliknij przycisk Przeniesienie.


