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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b100d5da6ec26dc386c0c6cb0793245531eb0d8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186263"
---
# <a name="create-account-structures"></a>Tworzenie struktur kont

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

