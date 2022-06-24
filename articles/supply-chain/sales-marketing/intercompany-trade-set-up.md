---
title: Konfigurowanie handlu międzyfirmowego
description: W tym artykule wyjaśniono, jak skonfigurować handel między firmami
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8d956c60db9f3acf2f1759dc3e1922da40d8a514
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905639"
---
# <a name="set-up-intercompany-trade"></a>Konfigurowanie handlu międzyfirmowego

[!include [banner](../../includes/banner.md)]

Aby uruchomić funkcje międzyfirmowe w systemie Microsoft Dynamics 365 Supply Chain Management, należy odpowiednio skonfigurować rekordy odbiorców i dostawców. Musisz również skonfigurować zobowiązania, należności, zamówienia i zaopatrzenie oraz sprzedaż i marketing.

## <a name="before-you-set-up-intercompany-trade"></a>Przed utworzeniem handlu między firmami

Przed skonfigurowaniem handlu międzyfirmowego należy zdecydować, którzy klienci są klientami międzyfirmowymi, a którzy dostawcy są dostawcami międzyfirmowymi. Dla każdej firmy w Microsoft Dynamics 365 Supply Chain Management musisz zdecydować, które zasady handlowe zastosować do międzyfirmowej relacji handlowej z określonym międzyfirmowym klientem lub dostawcą.

W szczególności zalecamy, abyś Ty i Twoja organizacja zapoznali się z parametrami międzyfirmowymi.

- Omów konsekwencje konfiguracji z menedżerami odpowiedzialnymi za handel międzyfirmowy w każdym podmiocie prawnym.
- Skonfiguruj odpowiednie wartości dla każdej firmy.

## <a name="set-up-trading-relations"></a>Ustawianie relacji handlowych

Aby skonfigurować handel międzyfirmowy dla odbiorców i dostawców, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Umożliwia wybór konta odbiorcy.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Określ parametry ustawień międzyfirmowych dla konta odbiorcy. Te parametry obejmują firmy, która zawiera odpowiedniego dostawcę i konto dostawcy. Parametry obejmują również zasady zamówień zakupu, zasady zamówień sprzedaży, mapowanie wartości oraz zasady umów sprzedaży i umów zakupu. Określasz również, czy używać wartości danych podstawowych z konta odbiorcy, czy z konta dostawcy w innej firmie.
1. Powtórz kroki od 1 do 4 dla pozostałych klientów międzyfirmowych w firmie.
1. Przejdź do pozycji **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**.
1. Wybierz konto dostawcy.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Określ parametry ustawień międzyfirmowych dla konta dostawcy. Te parametry obejmują podmiot prawny zawierający odpowiedniego klienta i konto klienta. Parametry obejmują również zasady zamówień sprzedaży, zasady zamówień zakupu, mapowanie wartości oraz zasady umów zakupu i umów sprzedaży. Określasz również, czy używać wartości danych podstawowych z konta dostawcy, czy z konta odbiorcy w innej firmie.
1. Powtórz kroki od 6 do 9 dla pozostałych dostawców międzyfirmowych w firmie.

## <a name="set-up-products"></a>Konfigurowanie produktów

Aby skonfigurować handel międzyfirmowy dla odbiorców i dostawców, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Zarządzanie informacjami o produktach \> Produkty \> Wszystkie produkty i produkty główne**.
1. Zdefiniuj produkty, które są zwalniane do podmiotów prawnych, w których chcesz prowadzić handel międzyfirmowy.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
