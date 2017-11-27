--- 
title: "Obliczanie amortyzacji środka trwałego we wszystkich firmach"
description: "Ta procedura przedstawia sposób ustawiania i uruchamiania procesu amortyzacji dla wielu firm."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Obliczanie amortyzacji środka trwałego we wszystkich firmach

[!include[task guide banner](../../includes/task-guide-banner.md)]

Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku. Ta procedura przedstawia sposób ustawiania i uruchamiania procesu dla wielu firm. Wykorzystuje rolę księgowego.  

To nagranie wykorzystuje firmę demonstracyjną USMF.


Kroki (16) podzadania: ustawianie arkuszy uruchomienia amortyzacji w całej firmie. 

1. Najpierw należy ustawić arkusze używane do uruchomienia amortyzacji w całej firmie dla każdej firmy. Wybierz kolejno opcje Środki trwałe > Ustawienia > Parametry środków trwałych. 
2. Rozwiń sekcję Propozycje środków trwałych. 
3. Utwórz rekord z nazwą arkusza używanego, który ma być używany dla każdej warstwy księgowania w firmie. Jeżeli księgi nie są księgowane w księdze głównej, należy wybrać warstwę księgowania Brak z powiązanym arkuszem. Kliknij przycisk Dodaj. 
4. W polu Warstwa księgowania wprowadź lub wybierz wartość. 
5. Wprowadź lub wybierz wartość w polu Nazwa arkusza. 
6. Powtórz ustawianie arkusza na stronie Parametry środków trwałych w każdej firmie. 

Podzadanie: obliczanie amortyzacji

1. Użyj strony Utwórz propozycję amortyzacji, aby uruchomić amortyzację w firmach. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji. 
2. W polu Warstwa księgowania wprowadź lub wybierz wartość. 
3. Nazwa arkusza przyjmie wartość domyślną z parametrów środków trwałych. Można ją zmienić tutaj dla bieżącej firmy. 
4. Wprowadź datę w polu Do dnia. 
5. Wybierz firmy, które mają zostać uwzględnione w uruchomieniu amortyzacji. Na liście będą widoczne tylko firmy z arkuszami ustawionymi dla propozycji środków trwałych na stronie Parametry środków trwałych. 
6. Po włączeniu opcja Zaksięguj arkusze automatycznie zaksięguje arkusze amortyzacji po utworzeniu. Jeżeli nie zostanie wybrana, arkusze zostaną utworzone bez księgowania, co umożliwi przejrzenie szczegółów przed zaksięgowaniem. Wybierz opcję Tak w polu Zaksięguj arkusze. 
7. Pola filtrowania obejmują wszystkie środki trwałe, grupy i księgi dla firm wybranych do tego uruchomienia amortyzacji. 
8. Opcja Przetwarzanie wsadowe jest domyślnie włączona. Gdy ta opcja jest włączona, tworzenie i księgowanie arkusza amortyzacji zostanie uruchomione w tle. 
9. Kliknij opcję Utwórz arkusz. 
10. Należy wyświetlić arkusze amortyzacji utworzone w określonych firmach. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.

