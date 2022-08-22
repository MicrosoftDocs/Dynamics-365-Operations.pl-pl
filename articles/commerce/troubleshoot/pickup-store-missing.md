---
title: Sklep detaliczny nie jest wyświetlany na liście sklepów, z których ma być odbiór
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy sklep detaliczny nie jest wyświetlany na liście sklepów, w których można odbierać towary.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: b6cec3d9d598be221516506388e4797ad579a610
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286760"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>Sklep detaliczny nie jest wyświetlany na liście sklepów, z których ma być odbiór

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy sklep detaliczny nie jest wyświetlany na liście sklepów, w których można odbierać towary.

## <a name="description"></a>opis

Sklep detaliczny nie jest wyświetlany na liście sklepów, w których towary mogą zostać odebrane.

## <a name="resolution"></a>Rozdzielczość

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Konfigurowanie długości geograficznej i szerokości geograficznej dla adresu sklepu w programie Commerce Headquarters

Aby skonfigurować długość i szerokość geograficzną adresu sklepu w siedzibie Commerce, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Sklepy \> Wszystkie sklepy**.
1. Znajdź sklep, który ma być wyświetlany wśród opcji pobrania w witrynie e-commerce. Należy zwrócić uwagę na wartość **Numeru jednostki operacyjnej**.
1. Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Jednostki operacyjne**.
1. Wyszukaj numer jednostki operacyjnej, opisano wcześniej, a następnie wybierz jednostkę operacyjną w wynikach wyszukiwania.
1. Na skróconej karcie **Adresy** wybierz opcję **Więcej opcji**, a następnie wybierz pozycję **Zaawansowane**.
1. Na skróconej karcie **Ogólne** upewnij się, że pola **Długość** i **Szerokość** są poprawnie ustawione. W ramach tego kroku upewnij się, że wartości zostały poprawnie określone jako liczby dodatnie lub ujemne.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Konfigurowanie grup realizacji w programie Commerce Headquarters

Aby skonfigurować grupy realizacji w Commerce headquarters, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.
1. Wybierz sklep internetowy do skonfigurowania.
1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.
1. Na stronie **Przypisania grupy realizacji** wybierz grupę realizacji dla sklepu internetowego.
1. W obszarze **Ustawienia** upewnij się, że sklep sieci sprzedaży jest poprawnie skonfigurowany dla grupy realizacji.

## <a name="additional-resources"></a>Dodatkowe zasoby 

[Tworzenie jednostki operacyjnej](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)

[Konfigurowanie kanału online](../channel-setup-online.md)
