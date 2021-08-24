---
title: Omówienie fakturowania elektronicznego
description: W tym temacie przedstawiono informacje na temat funkcji Faktur elektronicznych w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: eebe51ae89326965235c031ed11008c6af3d453f0f297d3201862946ab4caca9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741515"
---
# <a name="electronic-invoicing-overview"></a>Omówienie fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

Faktury elektroniczne dla Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management to hiperskalowalna usługa dla wielu dzierżawców, która umożliwia konfigurowalne przetwarzanie elektronicznych faktur i konfigurowalną wymianę dokumentów. Reguły przetwarzania i integracji są w pełni konfigurowalne, a logika działa poza rozwiązaniami Finance and Supply Chain Management. Usługa jest ukierunkowana głównie na przetwarzanie faktur elektronicznych w scenariuszach między przedsiębiorstwami a instytucjami rządowymi, ale można ją skonfigurować na zamówienie do innych celów.

Faktury elektroniczne może pomóc w osiągnięciu następujących celów:

- Szybkie i łatwe przyjęcie wymagań specyficznych dla kraju/regionu
- Standaryzowane implementacje rozwiązania Faktur elektronicznych
- Ulepszona możliwość śledzenia historii dokumentów
- Krótszy cykl implementacji
- Obniżony całkowity koszt użytkowania (TCO)
- Łatwe do regulowania konfiguracje, które nie wymagają zmiany kodu
- Uproszczone pakowanie konfiguracji
- Wbudowana funkcja eksportowania, importowania i integrowania oraz łatwa rozszerzalność w przetwarzaniu dokumentów faktur elektronicznych
- Łatwe ponowne wykorzystanie tych samych konfiguracji eksportu, importu i integracji w różnych firmach

Aby korzystać z funkcji Faktury elektroniczne, należy go zainstalować z projektu w Microsoft Dynamics Lifecycle Services (LCS). Następnie postępuj zgodnie z procedurą konfiguracji, aby włączyć integrację z Finance lub Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z Fakturami elektronicznymi](e-invoicing-get-started.md).

## <a name="service-availability"></a><a name="availability"></a>Dostępność usługi

Obecnie Fakturowanie elektroniczne jest dostępne dla klientów za pośrednictwem programu podglądowego, a w kolejnej fazie usługa stanie się ogólnodostępna. Ponieważ funkcjonalność, która spełnia wymagania specyficzne dla kraju/regionu, może być ograniczona na różnych etapach wydania, należy zawsze sprawdzać najbardziej aktualną dokumentację, która podkreśla zakres i zakres obsługiwanych rozwiązań specyficznych dla kraju/regionu.

Faktury elektroniczne są wdrażane w następujących lokalizacjach geograficznych platformy Azure:

- Stany Zjednoczone
- Europa

> [!NOTE]
> Faktury elektroniczne nie obsługuje wdrożeń lokalnych.

## <a name="extended-configurability"></a>Rozszerzona konfigurowalność

Faktur elektronicznych można używać w scenariuszach, w których należy utworzyć i wysłać dokument elektroniczny do wyznaczonych stron. Jest przeznaczony specjalnie do uruchamiania operacji konfigurowania przepływu na podstawie otrzymanych danych. Opcje konfigurowalności dostępne w rozwiązaniu Finance i Supply Chain Management są ograniczone do transformacji dokumentów. Usługa rozszerza te opcje, dodając konfigurowalne integracje, które są w niej dostępne. Ponadto wszystkie funkcje faktur elektronicznych, które były wcześniej dostępne, takie jak Brazilian Nota fiscal eletrônica (NF-e), Mexican Comprobante Fiscal Digital por Internet (CFDI) lub inne zachodnioeuropejskie Universal Business Language (UBL)/Pan-European Public Public Funkcje Procurement OnLine (PEPPOL) będą wykorzystywać konfiguracje do eksportu i importu oraz umożliwią integrację z zewnętrznymi usługami internetowymi.

## <a name="feature-highlights"></a>Najważniejsze cechy

- Bezpośrednia integracja z Finance i Supply Chain management
- Spójne środowisko użytkownika w zakresie konfiguracji i monitorowania procesu fakturowania elektronicznego we wszystkich krajach lub regionach
- Szybsze, łatwiejsze i tańsze wdrażanie rozwiązań faktur elektronicznych w nowych krajach lub regionach
- Konfiguracja usługi za pośrednictwem Regulatory Configuration Service (RCS) i konfiguracji funkcji globalizacji
- Przekształcenie danych biznesowych w wiele formatów faktur elektronicznych (XML, JavaScript Object Notation \[JSON\], TXT i wartości rozdzielane przecinkami \[CSV\]) przy użyciu konfiguracji zdefiniowanych w RCS:

    - Formaty raportowania elektronicznego, które są dostępne dla krajów lub regionów, w których nie jest dostępna konfigurowalność przekształcania faktur elektronicznych

- Konfigurowalne przesyłanie faktur elektronicznych do zewnętrznych usług internetowych, w tym obsługa certyfikacji za pomocą podpisów cyfrowych:

    - Wbudowana, łatwo rozszerzalna i konfigurowalna integracja z dodatkowymi treściami dla kilku krajów

    > [!NOTE]
    > Obecnie jest obsługiwanych ograniczona liczba przesłanek bezpośrednich. Więcej informacji znajduje się w sekcji [Dostępność usługi](#availability) we wcześniejszej części tego tematu. Pomoc zostanie przedłużona w przyszłości.

- Obsługa odpowiedzi z usług internetowych, w tym konfigurowalna obsługa komunikatów wyjątków
- Obsługa podpisów elektronicznych (na przykład przy użyciu algorytmu podpisywania XMLDSig)
- Przetwarzanie wsadowe wiadomości faktur elektronicznych

## <a name="architecture-and-data-flow"></a>Architektura i przepływ danych

Gdy funkcja Faktury elektroniczne jest instalowana z LCS i wymagana konfiguracja jest zakończona we wszystkich wymaganych aplikacjach, nawiązywane jest bezpieczne połączenie. Usługa znajduje się obecnie w centrach danych w Stanach Zjednoczonych i Europie. Dlatego lokalizacja usługi może różnić się od lokalizacji powiązanej instancji rozwiązania Finance lub Supply Chain Management. Po zakończeniu konfiguracji Faktury elektroniczne i włączeniu integracji, za każdym razem, gdy wysyłana jest faktura elektroniczna, dane podstawowe i dane transakcyjne, które są powiązane z określonym dokumentem, są wysyłane do Faktur elektronicznych.

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

Na poniższej ilustracji przedstawiono przepływ danych do i z Faktur elektronicznych.

![Przepływ danych dla Faktur elektronicznych.](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Klauzula prywatności
Włączenie i używanie Faktur elektronicznych może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Zostaną one przesłane do agencji zewnętrznych upoważnionych przez organy podatkowe w celu wysyłania faktur elektronicznych w predefiniowanych formatach wymaganych do integracji z usługami internetowymi tych rządów. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby
- [Administracja usługi](e-invoicing-service-administration.md)
- [Skonfiguruj faktury elektroniczne w RCS](e-invoicing-configuration-rcs.md)
- [Wystawiaj faktury elektroniczne w Finance i Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
