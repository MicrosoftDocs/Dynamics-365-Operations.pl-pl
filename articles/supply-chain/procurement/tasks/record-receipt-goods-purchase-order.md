---
title: Rejestrowanie przyjęcia towarów w zamówieniu zakupu
description: W tym temacie pokazano sposób rejestrowania przyjęcia towarów bezpośrednio w zamówieniu zakupu.
author: FrankDahl
manager: AnnBe
ms.date: 07/09/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e81bb3fe95326636c28885d4decad69f841e3db
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844016"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Rejestrowanie przyjęcia towarów w zamówieniu zakupu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie pokazano sposób rejestrowania przyjęcia towarów bezpośrednio w zamówieniu zakupu. Istnieje również możliwość rejestrowanie przyjęcia produktów w magazynie, a później zarejestrowania go w zamówieniu zakupu. To zadanie jest zwykle wykonywane przez pracownika działu zakupów lub osobę odpowiedzialną za rozrachunki z dostawcami. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. W przykładzie uwzględniono kroki utworzenia prostego zamówienie zakupu, dzięki czemu można odtworzyć procedurę jako przewodnik po zadaniu. Jeśli wykonujesz procedurę przy użyciu danych swojej firmy, zacznij od podzadania **Rejestrowanie przyjęcia towarów**.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Przygotowywanie nowego zamówienia zakupu w celu przyjęcia towarów
1. Wybierz kolejno **okienko nawigacji> Moduły > Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto dostawcy** wpisz wartość `US-101`.
4. Kliknij przycisk **OK**.
5. W polu **Numer pozycji** wpisz `M0001`.
6. W polu **Ilość** wpisz wartość `5`.
7. W okienku akcji wybierz **Zakup**.
8. Wybierz opcję **Potwierdź**.

## <a name="record-receipt-of-goods"></a>Rejestrowanie przyjęcia towarów
1. W okienku akcji wybierz pozycję **Odbierz**.
2. Wybierz pozycję **Przyjęcie produktu**. W polu **Ilość** można wybrać różne opcje dotyczące ilości, która ma zostać przyjęta. Na przykład jeśli ilość została wcześniej zarejestrowana w magazynie, można wybrać opcję **Ilość zarejestrowana**. W tym przykładzie należy użyć wartości **Ilość zamówiona**.
3. Rozwiń sekcję **Przegląd**.
4. W polu **Dokument przyjęcia** produktów wpisz dowolną wartość. To pole służy do wprowadzania odwołania, które będzie używane jako załącznik dla arkusza dokumentu przyjęcia produktów.  
5. Rozwiń sekcję **Wiersze**.
6. W polu **Ilość** wpisz wartość 4. W tym miejscu można ręcznie określić ilość przyjmowaną dla każdego wiersza zamówienia.  
7. Kliknij przycisk **OK**. Towary zostały teraz zarejestrowane jako przyjęte w zamówieniu zakupu, a w celu odzwierciedlenia tego utworzono arkusz dokumentu przyjęcia produktów. Można użyć akcji Dokument przyjęcia produktów, aby przejrzeć arkusze utworzone z zamówieniem zakupu i sprawdzić, co zostało przyjęte i kiedy.  

