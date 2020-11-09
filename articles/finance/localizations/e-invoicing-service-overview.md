---
title: Omówienie dodatku Faktur elektronicznych
description: W tym temacie przedstawiono informacje na temat dodatku Faktur elektronicznych w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffd48e173b66cc6d2571e666d5452a5eff05176c
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039753"
---
# <a name="electronic-invoicing-add-on-overview"></a>Omówienie dodatku Faktur elektronicznych

[!include [banner](../includes/banner.md)]

Dodatek Faktury elektroniczne dla Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management to hiperskalowalna usługa dla wielu dzierżawców, która umożliwia konfigurowalne przetwarzanie elektronicznych faktur i konfigurowalną wymianę dokumentów. Reguły przetwarzania i integracji są w pełni konfigurowalne, a logika działa poza rozwiązaniami Finance and Supply Chain Management. Usługa jest ukierunkowana głównie na przetwarzanie faktur elektronicznych w scenariuszach między przedsiębiorstwami a instytucjami rządowymi, ale można ją skonfigurować na zamówienie do innych celów.

Dodatek Faktury elektroniczne może pomóc w osiągnięciu następujących celów:

- Szybkie i łatwe przyjęcie wymagań specyficznych dla kraju/regionu
- Standaryzowane implementacje rozwiązania dodatkowego Faktur elektronicznych
- Ulepszona możliwość śledzenia historii dokumentów
- Krótszy cykl implementacji
- Obniżony całkowity koszt użytkowania (TCO)
- Łatwe do regulowania konfiguracje, które nie wymagają zmiany kodu
- Uproszczone pakowanie konfiguracji
- Wbudowana funkcja eksportowania, importowania i integrowania oraz łatwa rozszerzalność w przetwarzaniu dokumentów faktur elektronicznych
- Łatwe ponowne użycie tych samych konfiguracji eksportu, importu i integracji między firmami

Aby korzystać z dodatku Faktury elektroniczne, należy go zainstalować z projektu w Microsoft Dynamics Lifecycle Services (LCS). Następnie postępuj zgodnie z procedurą konfiguracji, aby włączyć integrację z Finance lub Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z dodatkiem Faktury elektroniczne](e-invoicing-get-started.md).

## <a name="availability"></a>Dostępność

Początkowo dodatek Faktury elektroniczne jest dostępny dla wybranych klientów za pośrednictwem programu podglądowego. Później wersja zapoznawcza zostanie udostępniona dla szerszego grona klientów. Na koniec usługa stanie się ogólnie dostępna. Ponieważ funkcjonalność, która spełnia wymagania specyficzne dla kraju/regionu, może być ograniczona na różnych etapach wydania, należy zawsze sprawdzać najbardziej aktualną dokumentację, która podkreśla zakres i zakres obsługiwanych rozwiązań specyficznych dla kraju/regionu.

Dodatek Faktury elektroniczne jest wdrażany w następujących lokalizacjach geograficznych platformy Azure:

- Stany Zjednoczone
- Europa

> [!NOTE]
> Dodatek Faktury elektroniczne nie obsługuje wdrożeń lokalnych.

## <a name="extended-configurability"></a>Rozszerzona konfigurowalność

Dodatku Faktury elektroniczne można używać w scenariuszach, w których należy utworzyć i wysłać dokument elektroniczny do wyznaczonych stron. Jest przeznaczony specjalnie do uruchamiania operacji konfigurowania przepływu na podstawie otrzymanych danych. Opcje konfigurowalności dostępne w rozwiązaniu Finance i Supply Chain Management są ograniczone do transformacji dokumentów. Usługa rozszerza te opcje, dodając konfigurowalne integracje, które są w niej dostępne. Ponadto wszystkie funkcje faktur elektronicznych, które były wcześniej dostępne, takie jak Brazilian Nota fiscal eletrônica (NF-e), Mexican Comprobante Fiscal Digital por Internet (CFDI) lub inne zachodnioeuropejskie Universal Business Language (UBL)/Pan-European Public Public Funkcje Procurement OnLine (PEPPOL) będą wykorzystywać konfiguracje do eksportu i importu oraz umożliwią integrację z zewnętrznymi usługami internetowymi.

## <a name="feature-highlights"></a>Najważniejsze cechy

- Bezpośrednia integracja z Finance i Supply Chain management
- Spójne środowisko użytkownika w zakresie konfiguracji i monitorowania procesu fakturowania elektronicznego we wszystkich krajach lub regionach
- Szybsze, łatwiejsze i tańsze wdrażanie rozwiązań dodatkowych dla faktur elektronicznych w nowych krajach lub regionach
- Konfiguracja usługi za pośrednictwem Regulatory Configuration Service (RCS) i konfiguracji funkcji globalizacji
- Przekształcenie danych biznesowych w wiele formatów faktur elektronicznych (XML, JavaScript Object Notation \[JSON\], TXT i wartości rozdzielane przecinkami \[CSV\]) przy użyciu konfiguracji zdefiniowanych w RCS:

    - Formaty raportowania elektronicznego, które są dostępne dla krajów lub regionów, w których nie jest dostępna konfigurowalność przekształcania faktur elektronicznych

- Konfigurowalne przesyłanie faktur elektronicznych do zewnętrznych usług internetowych, w tym obsługa certyfikacji za pomocą podpisów cyfrowych:

    - Wbudowana, łatwo rozszerzalna i konfigurowalna integracja z dodatkowymi treściami dla kilku krajów

    > [!NOTE]
    > Obecnie jest obsługiwanych ograniczona liczba przesłanek bezpośrednich. Więcej informacji znajduje się w sekcji [Dostępność](#availability) we wcześniejszej części tego tematu. Pomoc zostanie przedłużona w przyszłości.

- Obsługa odpowiedzi z usług internetowych, w tym konfigurowalna obsługa komunikatów wyjątków
- Obsługa podpisów elektronicznych (na przykład przy użyciu algorytmu podpisywania XMLDSig)
- Przetwarzanie wsadowe wiadomości faktur elektronicznych

## <a name="architecture-and-data-flow"></a>Architektura i przepływ danych

Gdy dodatek Faktury elektroniczne jest instalowany z LCS i wymagana konfiguracja jest zakończona we wszystkich wymaganych aplikacjach, nawiązywane jest bezpieczne połączenie. Usługa znajduje się obecnie w centrach danych w Stanach Zjednoczonych i Europie. Dlatego lokalizacja usługi może różnić się od lokalizacji powiązanej instancji rozwiązania Finance lub Supply Chain Management. Po zakończeniu konfiguracji dodatku Faktury elektroniczne i włączeniu integracji, za każdym razem, gdy wysyłana jest faktura elektroniczna, dane podstawowe i dane transakcyjne, które są powiązane z określonym dokumentem, są wysyłane do dodatku Faktury elektroniczne.

> [!NOTE]
> Jeśli Twoja faktura elektroniczna lub jakikolwiek inny dokument zawiera dane osobowe, sprawdź, czy korzystanie z tej funkcji jest zgodne z Rozporządzeniem o ochronie danych osobowych (RODO) i innymi przepisami, które są związane z przekazywaniem danych osobowych.

### <a name="high-level-description-of-the-data-flow"></a>Ogólny opis przepływu danych

1. Klient wysyła do usługi najprostszy dokument biznesowy.
2. Na podstawie informacji kontekstowych otrzymanych od klienta usługa wybiera odpowiedni przepływ przetwarzania.
3. Usługa uruchamia akcje przetwarzania. Działania te mogą obejmować przekształcenie dokumentu biznesowego w fakturę elektroniczną, zastosowanie podpisu elektronicznego i przesłanie dokumentu do zewnętrznej usługi internetowej.
4. Wszystkie odebrane i przetworzone dokumenty są przechowywane w magazynie obiektów BLOB klienta systemu Azure.
5. Wszystkie wpisy tajne i certyfikaty dzierżawy, które były używane do przetwarzania, są przechowywane w magazynie kluczy Azure klienta.
6. Usługa dostarcza klientowi na żądanie informacji o stanie przetwarzania wysłanego dokumentu biznesowego.
7. Klient otrzymuje informacje o zakończeniu przetwarzania i udostępnia wszystkie informacje dziennika. Udostępnia również dokument, który został utworzony lub odebrany podczas przetwarzania przepływu.

Na poniższej ilustracji przedstawiono przepływ danych do i z dodatku Faktury elektroniczne.

![Przepływ danych dla dodatku Faktury elektroniczne](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Klauzula prywatności
Włączenie i używanie Faktur elektronicznych może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Zostaną one przesłane do agencji zewnętrznych upoważnionych przez organy podatkowe w celu wysyłania faktur elektronicznych w predefiniowanych formatach wymaganych do integracji z usługami internetowymi tych rządów. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Rozpocznij pracę z dodatkiem Faktury elektroniczne](e-invoicing-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii](e-invoicing-bra-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Meksyku](e-invoicing-mex-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Włoch](e-invoicing-ita-get-started.md)
- [Skonfiguruj dodatek Faktury elektroniczne](e-invoicing-setup.md)
