---
title: Kopiowanie produktów towarzyszących z istniejącej wersji formuły
description: W tej procedurze pokazano sposób kopiowania produktów towarzyszących z istniejącej wersji formuły do innej wersji formuły dla zwolnionego produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbcf2abc37441f9ff23e2b180c261831dfb79369
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829289"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a>Kopiowanie produktów towarzyszących z istniejącej wersji formuły

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób kopiowania produktów towarzyszących z istniejącej wersji formuły do innej wersji formuły dla zwolnionego produktu. Warunkiem wstępnym jest istnienie co najmniej jednej wersji formuły skojarzonej z produktami towarzyszącymi. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.


## <a name="find-a-released-product"></a>Znajdowanie zwolnionego produktu
1. Przejdź do okna Zwolnione produkty.
2. Kliknij przycisk Pokaż filtry.
    * Masz zamiar dodać pole Typ produkcji w oknie dialogowym Filtr.  
3. Kliknij przycisk Dodaj pole filtru, aby dodać pole Typ produkcji.
    * W następnym kroku należy ręcznie wprowadzić formułę w polu Typ produkcji, a następnie kliknąć przycisk Zastosuj. Spowoduje to ustawienie filtru listy zwolnionych produktów.  
4. W polu Typ produkcji ręcznie wprowadź formułę.
5. Kliknij polecenie Zastosuj.

## <a name="select-a-released-product"></a>Wybór zwalnianego produktu
1. Na liście znajdź i zaznacz odpowiedni rekord.
2. Kliknij opcję Wersje formuły.
    * W okienku akcji Inżynieria kliknij opcję Wersje formuły.  

## <a name="copy-co-products"></a>Kopiowanie produktów towarzyszących
1. W okienku akcji kliknij pozycję Wersja formuły.
2. Kliknij przycisk Produkty towarzyszące.
3. Kliknij opcję Kopiuj.
4. W polu Numer towaru wprowadź lub wybierz wartość.
5. W polu Wersja formuły wprowadź lub wybierz wartość.
6. Kliknij przycisk OK.
7. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]