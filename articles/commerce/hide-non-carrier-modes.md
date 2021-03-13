---
title: Ukrywanie metod dostawy bez przewoźnika z poziomu opcji wysyłki w punkcie sprzedaży
description: W tym temacie opisano opcję konfiguracji, która może zapobiegać wyświetlaniu metod dostawy bez przewoźnika podczas tworzenia zamówień wysyłek w aplikacji punktu sprzedaży.
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: fcacb4243e78607d19d2c57aff5debe04d85d6f2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009729"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Ukrywanie metod dostawy bez przewoźnika z poziomu opcji wysyłki w punkcie sprzedaży


[!include [banner](includes/banner.md)]

W tym temacie opisano opcję konfiguracji dostępną dla aplikacji punktu sprzedaży. Ta opcja konfiguracji umożliwia zmianę zachowania wyboru metody dostawy podczas tworzenia zamówień wysyłki w punkcie sprzedaży.

Użytkownicy tworzący zamówienia wysyłki klienta w punkcie sprzedaży mogą wybrać metodę dostawy dla wysyłki. Ta funkcja jest dostępna bez względu na to, czy wysyłane jest całe zamówienie, czy tylko wybrane wiersze.

Domyślnie okno dialogowe, w którym jest wybierana metoda dostawy, zawiera wszystkie prawidłowe metody dostawy dla kombinacji kanału, pozycji i adresu dostawy. Te metody dostawy są definiowane na stronie **Metody dostawy** w programie Headquarters (**Sprzedaż i marketing \> Ustawienia \> Distribution \> Metody dostawy**). Metody dostawy bez przewoźnika, takie jak **Wyniesienie** lub **Pobranie**, mogą również pojawiać się w oknie dialogowym jako opcje do wyboru.

Dodaliśmy jednak funkcję umożliwiającą ukrywanie metod dostawy bez przewoźnika w oknie dialogowym. Aby włączyć tę funkcję, na stronie **Parametry Commerce** na karcie **Zamówienia odbiorców** ustaw opcję **Pokazuj tylko opcje metod z przewoźnikiem na potrzeby wysyłania zamówień** na **Tak**. Po włączeniu tej funkcji i uruchomieniu odpowiednich zadań dystrybucji w celu zsynchronizowania informacji z bazą danych kanału metody dostawy bez przewoźnika nie będą wyświetlane podczas procesu tworzenia zamówień wysyłki w punkcie sprzedaży.
