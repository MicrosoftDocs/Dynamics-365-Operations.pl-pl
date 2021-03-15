---
title: Tworzenie struktur kont
description: Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a8df7d7d9c4555bf46ac1cc3f71695837b1369b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968596"
---
# <a name="create-account-structures"></a>Tworzenie struktur kont

[!include [banner](../../includes/banner.md)]

Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta. W krokach użyto danych firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Konfigurowanie struktur kont**.
2. W **okienku akcji** kliknij **Nowe**, aby otworzyć rozwijane okno dialogowe.
3. W polu **Struktura konta** wpisz nazwę opisującą przeznaczenie struktury konta.
4. W polu **Opis** wprowadź opis określający przeznaczenie struktury konta.
5. Kliknij **Utwórz**.
6. W **Segmenty i dozwolone wartości** kliknij przycisk **Dodaj segment**.
7. Na liście wymiary wybierz wymiar, który chcesz dodać do struktury konta.
8. Na końcu listy kliknij przycisk **Dodaj segment**.
9. W razie potrzeby powtórz kroki od 6 do 9.
10. W sekcji **Szczegóły dozwolonych wartości** wybierz segment w celu edytowania dozwolonych wartości.
    Na przykład kliknij pole **Konto główne**.  
11. W polu **Operator** wybierz opcję taką jak „zawiera się między” lub „zawiera”.
12. W polu **Wartość** wpisz wartość. Na przykład 600000.  
13. W polu **za pomocą** wpisz wartość. Na przykład 699999.  
14. W sekcji **Szczegóły dozwolonych wartości** kliknij przycisk **Zastosuj**.
15. W razie potrzeby powtórz kroki od 10 do 15.  
16. W sekcji **Szczegóły dozwolonych wartości** kliknij przycisk **Dodaj nowe kryteria**.
17. W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.
18. W polu **Wartość** wpisz wartość. Na przykład 033.  
19. W polu **za pomocą** wpisz wartość. Na przykład 034.  
20. Kliknij polecenie **Zastosuj**.
21. W siatce wybierz segment w celu edytowania dozwolonych wartości. Na przykład MPK.  
22. W **polu CostCenter** wpisz wartość. Na przykład 007..021.  
23. W **Segmenty i dozwolone wartości** kliknij przycisk **Dodaj**.
24. W polu **MainAccount** wpisz wartość. Na przykład 600000..699999.  
25. W siatce wybierz segment w celu edytowania dozwolonych wartości. Na przykład Dział.  
26. W polu Dział wpisz wartość. Na przykład 032.  
27. W polu CostCenter wpisz wartość. Na przykład 086.  
28. W **okienku akcji** kliknij pozycję **Weryfikuj**.
29. W **okienku akcji** kliknij pozycję **Aktywuj**.
30. Kliknij **Aktywacja**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]