---
title: Obliczanie podatku TDS w transakcjach międzyfirmowych
description: W tym temacie opisano proces, który jest używany do obliczania podatku potrąconego w źródle (TDS) dla transakcji międzyfirmowych w fazach.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: c978c84891a0c1ce5a079484eec24590283027c4
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407929"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>Obliczanie podatku TDS w transakcjach międzyfirmowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano proces, który jest używany do obliczania podatku potrąconego w źródle (TDS) dla transakcji międzyfirmowych w fazach.

Podczas tworzenia międzyfirmowego zamówienia zakupu lub zamówienia sprzedaży do obliczania kwoty podatku TDS jest używana domyślna grupa TDS zdefiniowana dla odbiorcy lub dostawcy. Kwota TDS jest księgowana na kontach rozrachunków z dostawcami lub należności po zaksięgowaniu faktury.

Dla międzyfirmowe zamówienie sprzedaży zakupu lub zamówienia zakupu jest automatycznie tworzone zamówienie zakupu lub zamówienie sprzedaży. Domyślna grupa TDS jest wyświetlana na zamówieniu międzyfirmowym, dzięki czemu można je obliczyć. Możesz zmienić grupę TDS. Fakturę można zakłać tylko wtedy, gdy kwota netto faktury na automatycznie utworzonym zamówieniu międzyfirmowym jest taka liczba jak kwota netto faktury na oryginalnym zamówieniu. (Kwota netto jest kwotą faktury po potrąceniu TDS.)

Na przykład faktura sprzedaży zostanie utworzona na 50 000 i zostanie do niej dołączona grupa TDS o wartości **10%**. Zaksięgowana kwota faktury wynosi 45 000, a zaksięgowana kwota TDS dla faktury sprzedaży to 5000. Zamówienie zakupu jest automatycznie tworzone dla międzyfirmowe zamówienie sprzedaży, do których jest dołączona grupa TDS w wysokości **10%**. Jeśli zmienisz wartość grupy TDS na **15%**, nie będzie można zakturować faktury, ponieważ kwota netto utworzonej automatycznie międzyfirmowe zamówienie sprzedaży nie odpowiada kwocie netto faktury z oryginalnego zamówienia sprzedaży.

Arkusz płatności utworzony dla faktury międzyfirmowej jest księgowany automatycznie. Ten arkusz płatności może być księgowany tylko wtedy, gdy kwota płatności netto w nim odpowiada kwocie płatności netto w oryginalnym arkuszu płatności.
