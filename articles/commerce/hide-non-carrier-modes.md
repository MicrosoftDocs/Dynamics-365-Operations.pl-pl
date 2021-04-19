---
title: Ukrywanie metod dostawy bez przewoźnika z poziomu opcji wysyłki w punkcie sprzedaży
description: W tym temacie opisano opcję konfiguracji, która może zapobiegać wyświetlaniu metod dostawy bez przewoźnika podczas tworzenia zamówień wysyłek w aplikacji punktu sprzedaży.
author: hhainesms
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: a5f08fc86dc093fd0ead219b808fa720a43f6b6b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797125"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Ukrywanie metod dostawy bez przewoźnika z poziomu opcji wysyłki w punkcie sprzedaży


[!include [banner](includes/banner.md)]

W tym temacie opisano opcję konfiguracji dostępną dla aplikacji punktu sprzedaży. Ta opcja konfiguracji umożliwia zmianę zachowania wyboru metody dostawy podczas tworzenia zamówień wysyłki w punkcie sprzedaży.

Użytkownicy tworzący zamówienia wysyłki klienta w punkcie sprzedaży mogą wybrać metodę dostawy dla wysyłki. Ta funkcja jest dostępna bez względu na to, czy wysyłane jest całe zamówienie, czy tylko wybrane wiersze.

Domyślnie okno dialogowe, w którym jest wybierana metoda dostawy, zawiera wszystkie prawidłowe metody dostawy dla kombinacji kanału, pozycji i adresu dostawy. Te metody dostawy są definiowane na stronie **Metody dostawy** w programie Headquarters (**Sprzedaż i marketing \> Ustawienia \> Distribution \> Metody dostawy**). Metody dostawy bez przewoźnika, takie jak **Wyniesienie** lub **Pobranie**, mogą również pojawiać się w oknie dialogowym jako opcje do wyboru.

Dodaliśmy jednak funkcję umożliwiającą ukrywanie metod dostawy bez przewoźnika w oknie dialogowym. Aby włączyć tę funkcję, na stronie **Parametry Commerce** na karcie **Zamówienia odbiorców** ustaw opcję **Pokazuj tylko opcje metod z przewoźnikiem na potrzeby wysyłania zamówień** na **Tak**. Po włączeniu tej funkcji i uruchomieniu odpowiednich zadań dystrybucji w celu zsynchronizowania informacji z bazą danych kanału metody dostawy bez przewoźnika nie będą wyświetlane podczas procesu tworzenia zamówień wysyłki w punkcie sprzedaży.


[!INCLUDE[footer-include](../includes/footer-banner.md)]