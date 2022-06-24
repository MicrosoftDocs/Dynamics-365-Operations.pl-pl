---
title: Konfigurowanie dostawców, odbiorców i towarów dla handlu międzyfirmowego
description: W tym artykule wyjaśniono, jak skonfigurować dostawców, klientów i towary do handlu międzyfirmowego
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4c928435a4e66832b09dbc805664934cfb1236be
ms.sourcegitcommit: b666289f5113d0a3fa2220fe337d5aacf07cbd92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/08/2022
ms.locfileid: "8945763"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Konfigurowanie dostawców, odbiorców i towarów dla handlu międzyfirmowego

[!include [banner](../../includes/banner.md)]

Aby przygotować organizację do handlu międzyfirmowego, musisz zdefiniować dostawców i klientów, z którymi będziesz prowadzić handel wewnętrzny. Następnie należy skojarzyć tych dostawców i odbiorców z pozycjami, które będą kupowane lub sprzedawane.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**.
1. Wybierz dostawcę do zdefiniowania jako dostawca międzyfirmowy.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Określ parametry ustawień międzyfirmowych dla konta dostawcy. Do parametrów tych należą: firma i konto odbiorcy, zasady dotyczące zamówień sprzedaży, zasady dotyczące zamówień zakupu, mapowanie wartości oraz zasady dotyczące umów zakupu i umów sprzedaży. Określasz również, czy używać wartości danych podstawowych z konta dostawcy, czy z konta odbiorcy w innej firmie.
1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Na stronie listy **Zwolnione produkty** wybierz towary, które mają zostać przypisane do dostawcy, aby towary zostały dostępne w handlu międzyfirmowym. Dla każdego produktu otwórz stronę **Szczegóły zwolnionego produktu**. Na karcie **Zakup** w polu **Dostawca** wpisz numer dostawcy.
1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Wybierz klienta do zdefiniowania jako klienta międzyfirmowego.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Określ parametry ustawień międzyfirmowych dla konta odbiorcy. Parametry te obejmują podmiot prawny i konto dostawcy, zasady zamówień zakupu, zasady zamówień sprzedaży, mapowanie wartości oraz zasady umowy sprzedaży i umowy zakupu. Określasz również, czy używać wartości danych podstawowych z konta odbiorcy, czy z konta dostawcy w innej firmie.
1. Po skonfigurowaniu parametrów międzyfirmowych zamknij stronę **Międzyfirmowe**, aby powrócić do szczegółów dotyczących wybranego odbiorcy.
1. Rozwiń skróconą kartę **Dodatkowe szczegóły** i ustaw wartość **Tak** w ustawieniach *tworzenia zamówień międzyfirmowych*. Jeśli chcesz, aby zamówienia były również dostarczane bezpośrednio do klientów, ustaw **Dostawa bezpośrednia** na *Tak*.

    > [!NOTE]
    > Jeśli istnieją towary, które Twoja organizacja przechowuje i dostarcza klientom, możesz nie chcieć automatycznie tworzyć zamówień międzyfirmowych, nawet jeśli towar jest w magazynie. Aby wyłączyć automatyczne generowanie zamówień na pozycje, które czasami mogą znajdować się w magazynie, należy ustawić **Utwórz zamówienia między firmami** na *Nie*.

1. Jeśli chcesz zezwolić na tworzenie dodatkowych wierszy pośrednio na zamówieniu sprzedaży, ustaw **Twórz pośrednie wiersze zamówienia** na *Tak*. Użytkownik może następnie dodać wiersze do oryginalnego zamówienia sprzedaży z międzyfirmowego zamówienia sprzedaży.

> [!WARNING]
> Jeśli zezwolisz na pośrednie tworzenie wierszy zamówienia, zezwalasz na wszystkie dodatki do oryginalnego zamówienia sprzedaży z międzyfirmowego zamówienia sprzedaży. Każdy dodatek jest następnie przetwarzany do klienta i dodawany do zamówienia i faktury. Dodatkowo każdy dokument związany ze sprzedażą jest drukowany i księgowany automatycznie. Użytkownicy nie są powiadamiani o dodatku.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
