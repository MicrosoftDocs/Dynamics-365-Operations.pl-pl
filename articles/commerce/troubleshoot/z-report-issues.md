---
title: Problemy z uzgadnianiem danych w końcowym raporcie sprzedaży
description: W tym artykule opisano problemy, jakich mogą doświadczyć użytkownicy podczas uzgadniania danych raportu Z w Commerce headquarters. Opisuje również możliwe przyczyny źródłowe i rozwiązania, które mogą pomóc w zapobieganiu przyszłym sytuacjom.
author: Shajain
ms.date: 12/06/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 9803134c4c77233e565525e96fd82af293d4c829
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832134"
---
# <a name="issues-with-the-data-reconciliation-of-a-z-report"></a>Problemy z uzgadnianiem danych w końcowym raporcie sprzedaży

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku napotkania problemów z uzgadnianiem danych raportu Z w Microsoft Dynamics 365 Commerce headquarters. Opisuje problemy, jakich użytkownicy mogą doświadczyć podczas uzgadniania danych, możliwe przyczyny oraz rozwiązania, które mogą pomóc w uniknięciu takich sytuacji w przyszłości.

## <a name="description"></a>opis

- Występuje niezgodność między kwotami, które są wyświetlane w raporcie Z, a sumami, które są wyświetlane w obliczonym zestawieniu.
- Transakcja w centrali ma nieprawidłową liczbę pozycji lub występuje niezgodność między sumą pozycji a sumą transakcji.
- Liczba transakcji wykazanych w zmianie w centrali jest mniejsza niż liczba transakcji na raporcie Z.
- Wysłanie oświadczenia nie powiodło się z jednego z powyższych powodów.

### <a name="root-cause"></a>Przyczyna

Najczęstszą przyczyną opisanych wcześniej objawów jest generowanie duplikatów identyfikatorów transakcji w bazie danych kanału. Duplikaty identyfikatorów transakcji mogą być generowane z następujących powodów:

- Lokalna baza danych Modern Point of Sale (MPOS) jest uszkodzona.
- W systemie MPOS niektóre transakcje odbywają się w trybie offline, a jego reaktywacja odbywa się za pomocą konta, które nie ma dostępu do bazy danych offline.
- Istnieje problem z dostosowywaniem, który jest związany z generowaniem identyfikatorów transakcji.

## <a name="resolution"></a>Rozwiązanie

Zazwyczaj Commerce wykorzystuje sekwencję liczb do generowania kolejnych identyfikatorów transakcji. Jeśli z jakiegoś powodu system nie może ustalić, czy użyto sekwencji numerów, generowany jest duplikat ID transakcji. 

Aby rozwiązać problem zduplikowanych identyfikatorów transakcji, utwórz zgłoszenie do pomocy technicznej, aby sprawdzić, czy można naprawić dane transakcji. W niektórych przypadkach, np. gdy nie ma utraty danych w centrali, nie jest możliwe ani wymagane ich naprawienie.

Aby zapobiec temu problemowi w przyszłości, musisz włączyć w centrali funkcję **Włącz nowy identyfikator transakcji, aby uniknąć powielania identyfikatorów transakcji**. Ta funkcja została dodana w wersji Commerce 10.0.19. Zapobiega to tworzeniu kolejnych identyfikatorów transakcji, ponieważ dla każdej transakcji tworzony jest unikalny identyfikator. Aby uzyskać więcej informacji o tej funkcji, zobacz temat [Zapobieganie powielaniu identyfikatorów transakcji](../channel-setup-retail.md#ensure-unique-transaction-ids).
