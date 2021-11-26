---
title: Przenoszenie plików NF-e XML jako załączników
description: W tym temacie wyjaśniono, jak przenieść pliki XML NF-e z bazy danych Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management i udostępnić je jako załączniki.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c7b82d486cecf6b20f1283fa609c360b3003efca
ms.sourcegitcommit: ebf6546835e4d6a80aea1dfae81e119e294387f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799451"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>Przenoszenie plików NF-e XML jako załączników

[!include [banner](../includes/banner.md)] 


Podczas wystawiania elektronicznych dokumentów fiskalnych (NF-e) tworzone są pliki XML i przechowywane w bazach danych Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management. W lokalizacji brazylijskiej można użyć funkcji **przenoszenia xml NF-e jako załącznika**, aby wolne miejsce w bazie danych wykorzystywane przez te pliki XML.

Dla określonego zakresu dat i domicylności podatkowej funkcja przenosi pliki XML NF-e z bazy danych Finance lub Supply Chain Management do magazynu obiektów Blob z subskrypcji systemu Azure. To ruch powoduje, że pliki są dostępne tylko jako załączniki. Pliki XML zostaną pomyślnie przeniesione do magazynu obiektów Blob, a oryginalne pliki zostaną usunięte z bazy danych Finance lub Supply Chain Management. W związku z tym jest zwalniana przestrzeń bazy danych, która jest używana przez te pliki.

Wykonaj poniższe czynności, aby włączyć funkcję **NF-e XML move jako załącznik**.

1. Włącz funkcję **Fakturowanie elektroniczne** w Finance lub Supply Chain Management
2. Na karcie **Wszystkie** wyszukaj i wybierz element **NF-e XML jako funkcję załączników**.
3. Wybierz **Włącz teraz**.

Aby przenieść pliki NF-e XML jako załączniki, należy wykonać następujące kroki.

1. Przejdź do **Rozrachunki z odbiorcami** \> **Dokumenty fiskalne** \> **Elektroniczne dokumenty**\>**Przenoszenie dokumentów fiskalnych NF-e jako załączniki**.
2. Określ daty w polach **Od dnia** i **Do dnia**, aby zdefiniować okres serwisu.
3. W polu **Identyfikator domicylu fiskalnego** wprowadź lub wybierz wartość.
4. Kliknij przycisk **OK**.

> [!IMPORTANT]
> Proces nie jest odwracalny. Po przeniesieniu plików NF-e XML użytkownicy mogą je wyświetlić tylko przez wybranie **załączników** u góry strony **dokumentu fiskalnego**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
