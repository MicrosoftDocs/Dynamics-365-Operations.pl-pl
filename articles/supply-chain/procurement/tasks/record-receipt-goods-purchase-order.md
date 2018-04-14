--- 
title: "Rejestrowanie przyjęcia towarów w zamówieniu zakupu"
description: "W tej procedurze pokazano sposób rejestrowania przyjęcia towarów bezpośrednio w zamówieniu zakupu."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Rejestrowanie przyjęcia towarów w zamówieniu zakupu

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób rejestrowania przyjęcia towarów bezpośrednio w zamówieniu zakupu. Istnieje również możliwość rejestrowanie przyjęcia produktów w magazynie, a później zarejestrowania go w zamówieniu zakupu. To zadanie jest zwykle wykonywane przez pracownika działu zakupów lub osobę odpowiedzialną za rozrachunki z dostawcami. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. W przykładzie uwzględniono kroki utworzenia prostego zamówienie zakupu, dzięki czemu można odtworzyć procedurę jako przewodnik po zadaniu. Jeśli wykonujesz procedurę przy użyciu danych swojej firmy, zacznij od podzadania Rejestrowanie przyjęcia towarów.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Przygotowywanie nowego zamówienia zakupu w celu przyjęcia towarów
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wpisz wartość US-101.
4. Kliknij przycisk OK.
5. W polu Numer pozycji wpisz M0001.
6. W polu Ilość wpisz wartość 5.
7. W okienku akcji kliknij pozycję Zakup.
8. Kliknij przycisk Potwierdź.

## <a name="record-receipt-of-goods"></a>Rejestrowanie przyjęcia towarów
1. W okienku akcji kliknij pozycję Odbierz.
2. Kliknij opcję Dokument przyjęcia produktów.
    * W polu Ilość można wybrać różne opcje dotyczące ilości, która ma zostać przyjęta. Na przykład jeśli ilość została wcześniej zarejestrowana w magazynie, można wybrać opcję Ilość zarejestrowana.  W tym przykładzie należy użyć wartości Ilość zamówiona.   
3. W polu Dokument przyjęcia produktów wpisz dowolną wartość.
    * To pole służy do wprowadzania odwołania, które będzie używane jako załącznik dla arkusza dokumentu przyjęcia produktów.  
4. Rozwiń sekcję Wiersze.
5. W polu Ilość wpisz wartość 4.
    * W tym miejscu można ręcznie określić ilość przyjmowaną dla każdego wiersza zamówienia.  
6. Zwiń sekcję Wiersze.
7. Kliknij przycisk OK.
    * Towary zostały teraz zarejestrowane jako przyjęte w zamówieniu zakupu, a w celu odzwierciedlenia tego utworzono arkusz dokumentu przyjęcia produktów. Można użyć akcji Dokument przyjęcia produktów, aby przejrzeć arkusze utworzone z zamówieniem zakupu i sprawdzić, co zostało przyjęte i kiedy.  


