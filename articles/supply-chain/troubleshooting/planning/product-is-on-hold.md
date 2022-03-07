---
title: Produkt jest wstrzymany dla transakcji
description: Po skonfigurowaniu planowania zleceń pojawia się komunikat o błędzie informujący, że pozycja jest wstrzymana dla transakcji.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301286"
---
# <a name="product-is-on-hold-for-transactions"></a>Produkt jest wstrzymany dla transakcji

Kod błędu: SYS13295

## <a name="symptoms"></a>Objawy

Po ustaleniu planowanych zleceń pojawia się następujący komunikat o błędzie:

> Pozycja %1 jest zablokowana dla transakcji w %2.

## <a name="cause"></a>Powód

Opisując zablokowane towary, system używa terminów *zablokowany*, *zatrzymany* i *wstrzymany* zamiennie. Ten błąd oznacza, że w domyślnych ustawieniach zamówienia pozycja jest ustawiona jako **Zatrzymana**.

Jeśli pozycja jest zablokowana, a dodajesz ją do wiersza zamówienia zakupu lub zamówienia sprzedaży, otrzymujesz komunikat ostrzegawczy. Po zablokowaniu towaru transakcje magazynowe odnoszące się do wiersza zamówienia zakupu lub sprzedaży nie mogą być modyfikowane (na przykład podczas księgowania). Można zablokować kupiony towar i jednocześnie go sprzedać. W takim przypadku to pole **Zatrzymane** jest zaznaczone w zamówieniu zakupu, ale produkt nie jest zablokowany w magazynie i na zamówieniu sprzedaży.

Oto niektóre z warunków, które mogą spowodować, że numer pozycji zostanie zablokowany przed sprzedażą:

- Towar jest nadal projektowy lub wytwarzany. Dlatego nie chcesz, aby został sprzedany lub zarezerwowany.
- Otrzymałeś wiele wadliwych przedmiotów, a wady muszą zostać usunięte przed sprzedażą przedmiotu.

W związku z tym można zablokować towar do czasu rozwiązania problemu.

Jeśli towar jest zablokowany i tworzysz wiersz zamówienia zwrotu, zostanie wyświetlona wiadomość. Nie można zablokować serii lub partii towaru. Jeśli konieczne jest zablokowanie części towaru, można to zrobić przez przesunięcie magazynowe lub zablokowanie całego zapasu towaru na dany okres.

## <a name="resolution"></a>Rozwiązanie

- Otwórz stronę **Ustawienia domyślne zamówień** dla pozycji i wyczyść pole wyboru **Zatrzymane**.
