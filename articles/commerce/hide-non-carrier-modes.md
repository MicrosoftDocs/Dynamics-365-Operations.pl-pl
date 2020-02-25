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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 75e7e8f183982f7829db78eb75b8c29c9ab95e89
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023746"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="4dcb3-103">Ukrywanie metod dostawy bez przewoźnika z poziomu opcji wysyłki w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4dcb3-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4dcb3-104">W tym temacie opisano opcję konfiguracji dostępną dla aplikacji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="4dcb3-105">Ta opcja konfiguracji umożliwia zmianę zachowania wyboru metody dostawy podczas tworzenia zamówień wysyłki w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="4dcb3-106">Użytkownicy tworzący zamówienia wysyłki klienta w punkcie sprzedaży mogą wybrać metodę dostawy dla wysyłki.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="4dcb3-107">Ta funkcja jest dostępna bez względu na to, czy wysyłane jest całe zamówienie, czy tylko wybrane wiersze.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="4dcb3-108">Domyślnie okno dialogowe, w którym jest wybierana metoda dostawy, zawiera wszystkie prawidłowe metody dostawy dla kombinacji kanału, pozycji i adresu dostawy.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="4dcb3-109">Te metody dostawy są definiowane na stronie **Metody dostawy** w programie Headquarters (**Sprzedaż i marketing \> Ustawienia \> Distribution \> Metody dostawy**).</span><span class="sxs-lookup"><span data-stu-id="4dcb3-109">These modes of delivery are defined on the **Modes of delivery** page in Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="4dcb3-110">Metody dostawy bez przewoźnika, takie jak **Wyniesienie** lub **Pobranie**, mogą również pojawiać się w oknie dialogowym jako opcje do wyboru.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="4dcb3-111">Dodaliśmy jednak funkcję umożliwiającą ukrywanie metod dostawy bez przewoźnika w oknie dialogowym.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="4dcb3-112">Aby włączyć tę funkcję, na stronie **Parametry Commerce** na karcie **Zamówienia odbiorców** ustaw opcję **Pokazuj tylko opcje metod z przewoźnikiem na potrzeby wysyłania zamówień** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-112">To turn on this feature, on the **Commerce parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="4dcb3-113">Po włączeniu tej funkcji i uruchomieniu odpowiednich zadań dystrybucji w celu zsynchronizowania informacji z bazą danych kanału metody dostawy bez przewoźnika nie będą wyświetlane podczas procesu tworzenia zamówień wysyłki w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>
