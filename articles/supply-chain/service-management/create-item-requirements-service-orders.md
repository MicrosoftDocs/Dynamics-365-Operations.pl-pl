---
title: Tworzenie zapotrzebowań na towary na podstawie zleceń serwisowych
description: W tym artykule opisano sposób tworzenia zapotrzebowania na towary dla zleceń serwisowych.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c2c90ff76121b436d0fec532268cd3383de0eab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888420"
---
# <a name="create-item-requirements-for-service-orders"></a>Tworzenie zapotrzebowań na towary na podstawie zleceń serwisowych

[!include [banner](../includes/banner.md)]

Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom. Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia. Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.

Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.

Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu. W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem. Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można wyświetlić to zapotrzebowanie w formularzu **Projekty** dla wybranego projektu.

## <a name="create-an-item-requirement-for-a-service-order"></a>Tworzenie zapotrzebowania na towary dla zlecenia serwisowego

1. Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.
1. Wybierz zlecenie serwisowe, dla którego chcesz utworzyć zapotrzebowanie na towar.
1. W **okienku akcji** na karcie **Wysyłka** wybierz opcję **Zapotrzebowanie na towary**.
1. W formularzu **Zapotrzebowanie na towary** wprowadź informacje dla wymaganego towaru. Aby uzyskać więcej informacji o konkretnych polach, zobacz [Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Tworzenie zapotrzebowania na towary do umowy serwisowej

1. Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.
1. Otwórz umowę serwisową, dla której chcesz utworzyć zapotrzebowanie na towar.
1. Na skróconej karcie **Wiersze** wybierz **Dodaj**, aby utworzyć nowy wiersz.
1. W polu **Typ transakcji** wybierz opcję **Towar**.
1. W polu **Ustawienia pozycji** wybierz opcję **Zapotrzebowanie na towary**.
1. W polu **Numer pozycji** wybierz towar, który jest wymagany dla umowy serwisowej.
1. Na skróconej karcie **Szczegóły wiersza** na karcie **Wymiary produktu** w polu **Oddział** wybierz oddział zapasów dla towaru.
1. Aby utworzyć zlecenie serwisowe z wiersza umowy, na skróconej karcie **Wiersze** wybierz opcję **Utwórz zlecenia serwisowe**, a następnie wprowadź odpowiednie informacje w formularzu **Utwórz zlecenia serwisowe**.

## <a name="see-also"></a>Informacje dodatkowe

[Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
