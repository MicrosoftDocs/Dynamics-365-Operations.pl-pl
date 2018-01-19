--- 
title: "Tworzenie, obliczanie i księgowanie zestawienia dla sklepu sieci sprzedaży"
description: "Ta procedura prowadzi przez kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 42ab631e29a7fae1140acd41ad80c13e55ca1404
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a>Tworzenie, obliczanie i księgowanie zestawienia dla sklepu sieci sprzedaży

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura prowadzi przez kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu. Istnieją także zadania wsadowe, które można skonfigurować na potrzeby tych samych zadań. Kroki konfigurowania i wykonywania zadań wsadowych znajdują się w innych artykułach. Aby wykonać tę procedurę, muszą istnieć transakcji, które zostały wykonane w punkcie sprzedaży, a następnie pobrane do systemu Dynamics AX. Nagranie wykorzystuje dane firmy demonstracyjnej USRT. Ta procedura może się odwoływać do systemu Microsoft Dynamics AX. Należy zwrócić uwagę, że oprogramowanie Dynamics AX nosi obecnie nazwę Microsoft Dynamics 365 for Operations.

1. Wybierz kolejno opcje Wszystkie obszary robocze > .. > Finanse sklepu sieciowego.
2. Kliknij opcję Nowe zestawienie.
3. W polu Numer sklepu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wybranym wierszu.
5. Kliknij przycisk OK.
    * Grupa ustawień zawiera ustawienia kontrolujące, które transakcje są uwzględniane w zestawieniu i jak są grupowania w wiersze zestawienia. Można otworzyć grupę ustawień i zmienić te ustawienia lub można użyć ustawień domyślnych.  
    * Pole Metoda zestawienia określa sposób grupowania wierszy zestawienia.  
    * Wybierz pracownika lub kasę, aby obliczać zestawienie tylko dla określonego pracownika lub kasy.  
6. W polu Metoda zamknięcia wybierz opcję.
7. Kliknij opcję Oblicz zestawienie.
8. Kliknij przycisk Tak.
    * Po obliczeniu zestawienia powinny być utworzone wiersze z sumami kwot dla każdej użytej metody płatności i metody zestawienia.  
    * Wprowadź zliczoną kwotę w każdym wierszu, jeśli musi ona być wprowadzona lub zaktualizowana. Pole zliczenia jest wypełniane kwotami z deklaracji środków płatniczych sporządzonych w punkcie sprzedaży.  
9. Kliknij opcję Zaksięguj zestawienie.
10. Kliknij przycisk Zamknij.
11. Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Finanse sklepu sieciowego.
12. Kliknij kartę Zaksięgowane zestawienia.


