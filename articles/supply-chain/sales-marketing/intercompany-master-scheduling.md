---
title: Międzyfirmowe planowanie główne
description: W tym artykule wyjaśniono międzyfirmowe planowanie główne
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4993f981b268127af7c9259aa0e73a8e4a75015a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851457"
---
# <a name="intercompany-master-scheduling"></a>Międzyfirmowe planowanie główne

[!include [banner](../../includes/banner.md)]

Planowanie międzyfirmowe jest sposobem obliczania zapotrzebowania i generowania planowanych zamówień międzyfirmowych w kilku firmach wewnętrznych. Międzyfirmowe planowanie główne jest przeprowadzane na określonej liczbie iteracji. Aby system Microsoft Dynamics 365 Supply Chain Management przeprowadził międzyfirmowe planowanie główne, należy skonfigurować planowanie główne w każdym z przedsiębiorstw międzyfirmowych. Dzięki temu w określonej liczbie iteracji program Microsoft Dynamics 365 Supply Chain Management automatycznie utworzy międzyfirmowe zamówienie zakupu, a to będzie prowadziło do automatycznego utworzenia międzyfirmowego zamówienia sprzedaży, z którym związane są nowe wymagania.

Międzyfirmowe planowanie główne i kolejność planowania międzyfirmowego można określić za pomocą parametrów **Planowanie główne** każdego przedsiębiorstwa międzyfirmowego.

Aby propagować popyt w całym łańcuchu międzyfirmowym, należy ustawić parametry, aby upewnić się, że planowane zamówienia zakupu są automatycznie ustalane; oznacza to, że zamówienia nie mogą być zmieniane pod względem czasu ani ilości. Skonfiguruj **Przedział czasowy ujędrniania** w grupie Zasięg lub **Przedział czasowy ujędrniania** w planie głównym. Jeśli nie ustawiono **Przedział czasowy ujędrniania**, żadne międzyfirmowe zamówienia zakupu nie są tworzone automatycznie. Dopiero pierwsze wykonanie harmonogramu głównego skutkuje planowanymi zamówieniami. Jednak ponieważ nie jest tworzone żadne międzyfirmowe zamówienie zakupu, nie jest tworzone międzyfirmowe zamówienie sprzedaży, a zatem nie są już tworzone międzyfirmowe zamówienia zakupu i tak dalej.

Po uruchomieniu międzyfirmowego planowania głównego system Microsoft Dynamics 365 Supply Chain Management przeprowadzi międzyfirmowe planowanie główne w każdym przedsiębiorstwie międzyfirmowym, a następnie przeprowadzi drugie planowanie w każdym przedsiębiorstwie itd., aż do osiągnięcia określonej liczby iteracji. Maksymalnie możliwa jest liczba 30 iteracji, ale im więcej iteracji zostanie wybranych, tym dłuższy jest czas planowania.

Ponieważ planowanie główne w firmach jest kontrolowane przez sekwencję planowania międzyfirmowego, czyli kolejność, w jakiej program ustala priorytety harmonogramów głównych między każdą firmą międzyfirmową, można uruchomić międzyfirmowe planowanie główne z dowolnej firmy międzyfirmowej. Ponieważ kolejność planowania międzyfirmowego określa kolejność wykonywania planowania głównego w firmach, nie ma znaczenia, gdzie jest uruchamiane planowanie główne międzyfirmowe. W każdej iteracji bieżąca firma wykonuje ostatnie.

> [!NOTE]
> Najlepszą metodą jest uruchomienie międzyfirmowego planowania głównego z firmy, w której działa system Microsoft Dynamics 365 Supply Chain Management.

Na stronie **Międzyfirmowe planowanie główne** można uruchomić sekwencję planowania głównego, która uruchomi pierwsze planowanie główne z regułą aktualizacji obliczenia zapotrzebowania, która została wybrana dla pierwszej iteracji dla wszystkich przedsiębiorstw międzyfirmowych. Kolejne iteracje stosują następną regułę wybraną dla następnej iteracji, a ta reguła jest stosowana do momentu osiągnięcia określonej liczby iteracji.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
