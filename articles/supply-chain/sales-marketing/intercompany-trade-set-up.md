---
title: Konfigurowanie handlu międzyfirmowego
description: W tym temacie wyjaśniono, jak skonfigurować handel między firmami
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 75d6679152a056f6883658911f93464252e5fe87
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548459"
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
