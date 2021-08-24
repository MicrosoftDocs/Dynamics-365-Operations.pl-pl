---
title: Przenoszenie środka trwałego
description: W tym przewodniku po zadaniach zostaną przeniesienie informacje finansowe księgi środków trwałych z jednego zestawu wymiarów finansowych do nowego zestawu wymiarów finansowych.
author: saraschi2
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c307568ab1cc064c27fa8d3e24756f564947e4716aaed1c280019c1283da1c93
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765699"
---
# <a name="transfer-a-fixed-asset"></a>Przenoszenie środka trwałego

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]