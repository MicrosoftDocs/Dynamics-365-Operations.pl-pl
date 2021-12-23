---
title: Przenoszenie środka trwałego
description: W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e573386ddbb97bf60e2e501ba92b225f8716c73a
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883369"
---
# <a name="transfer-a-fixed-asset"></a>Przenoszenie środka trwałego

[!include [banner](../../includes/banner.md)]

W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.  

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
