---
title: Przenoszenie środka trwałego
description: W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 167591cf160916f256e2d10f122eca312ba07639
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186838"
---
# <a name="transfer-a-fixed-asset"></a>Przenoszenie środka trwałego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.  Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.

1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.
2. Na liście odszukaj i zaznacz środek trwały, który ma zostać przeniesiony.
3. W okienku akcji kliknij pozycję **Środek trwały**.
4. Kliknij opcję **Przenieś środki trwałe**.
5. W polu **Data przeniesienia** wprowadź datę.
6. Wprowadź komentarze opisujące przeniesienie.
    
    Ta lista przedstawia wszystkie księgi dla środka trwałego.  
7. Oznacz księgi, które mają zostać przeniesione do nowego zestawu wymiarów finansowych.
    * Ta lista przedstawia istniejące wartości wymiarów finansowych dla wybranej księgi.  
    * Zaznacz wymiar finansowy, który chcesz zaktualizować dla wybranej księgi środków trwałych.  
8. W polu **Wymiar finansowy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Ustaw wartości odpowiednich innych wymiarów finansowych.  
    * Po przeniesieniu zmieniają się wszystkie wartości wymiarów finansowych, niezależnie od tego, czy wartość została wprowadzona czy też pole było puste. Na przykład mogła być wprowadzono wartość wymiaru Jednostka biznesowa, a niewypełnione wymiary Centrum kosztów i Dział. Jeśli struktura konta pozwala na puste wartości wymiarów Centrum kosztu i Dział, przeniesienie spowoduje, że każdy model ewidencji otrzyma nową wartość wymiaru Jednostka biznesowa, a puste wartości wymiarów Centrum kosztów i Dział.  
9. Kliknij przycisk **Aktualizuj**.
    * Przed sfinalizowaniem przeniesienia masz możliwość podglądu efektów zmian.  
    * Przejrzyj wyniki przed przeniesieniem ksiąg środków trwałych.  
10. Kliknij przycisk **Przeniesienie**.

