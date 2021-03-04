---
title: Szczegółowe dane finansowe — strona główna (wersja zapoznawcza)
description: Moduł Szczegółowe dane finansowe udostępnia konfigurowalne i rozszerzalne modele, które pomagają dokładnie i inteligentnie przewidywać przepływy pieniężne w firmie, prognozować terminy otrzymania płatności za zaległe należności oraz generować propozycje budżetowe, które mogą przyspieszyć proces budżetowania. Wszystkie te funkcje są oparte na inteligentnych modelach uczenia maszynowego.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d7d167c4a8035231ea3c5630001d3aeccbcd7988
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644928"
---
# <a name="finance-insights-home-page-preview"></a>Szczegółowe dane finansowe — strona główna (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Moduł Szczegółowe dane finansowe udostępnia konfigurowalne i rozszerzalne modele, które pomagają dokładnie i inteligentnie przewidywać przepływy pieniężne w firmie, prognozować terminy otrzymania płatności za zaległe należności oraz generować propozycje budżetowe, które mogą przyspieszyć proces budżetowania. Wszystkie te funkcje są oparte na inteligentnych modelach uczenia maszynowego. Gdy te nowe możliwości zostaną połączone z mechanizmami automatyzacji w funkcjach płatności dla dostawców i windykacji, powstaje rozbudowany i inteligentny system finansowy, który wspiera podejmowanie decyzji i pomaga podejmować działania w celu skutecznego reagowania na obecne i przewidywane wyzwania biznesowe.

Wersja zapoznawcza Finance Insights jest dostępna dla wdrożeń próbnych w Stanach Zjednoczonych Ameryki, Europie i Zjednoczonym Królestwie. Firma Microsoft stopniowo zwiększa obsługę wielu regionów.

Funkcje wersji zapoznawczej mogą być i powinny być włączone tylko w środowiskach piaskownicy warstwy 2. Nie można migrować ustawień i modeli sztucznej inteligencji (AI) utworzonych w środowisku piaskownicy do środowiska produkcyjnego. Aby uzyskać więcej informacji, zobacz [Uzupełniające warunki użytkowania wersji zapoznawczych Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/legal/supp-dynamics365-preview#:~:text=Supplemental%20Terms%20of%20Use%20for%20Microsoft%20Dynamics%20365,%28governing%20your%20use%20of%20Microsoft%20Dynamics%20365%20Online%29.).

## <a name="prerequisites"></a>Wymagania wstępne

Ta sekcja zawiera listę wymagań dotyczących korzystania z modułu Szczegółowe dane finansowe. Tam, gdzie to możliwe, udostępniono łącza do źródeł dodatkowych informacji.

### <a name="legal-requirements"></a>Wymagania prawne

Aby zawnioskować o udział w programie zapoznawczym, wypełnij [umowę na korzystanie z wersji zapoznawczej modułu Szczegółowe dane finansowe w rozwiązaniu Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u)

### <a name="system-requirements"></a>Wymagania systemowe

Do korzystania z wersji zapoznawczej modułu Szczegółowe dane finansowe jest wymagane środowisko piaskownicy warstwy 2 (wielostanowiskowe). Aby uzyskać informacje kontekstowe o środowiskach, należy zapoznać się z tematem [Planowanie środowiska](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/imp-lifecycle/environment-planning).

### <a name="version-requirements"></a>Wymagania dotyczące wersji

Ten dokument dotyczy wersji 10.0.11 aplikacji rozwiązania Finance and Operations (aktualizacja platformy 35) i nowszych wersji.

### <a name="historical-data-requirements"></a>Wymagania dotyczące danych historycznych

Do poprawnego wytrenowania modelu uczenia maszynowego, który jest używany przez funkcję prognozowania płatności od odbiorców, są potrzebne faktury od odbiorców co najmniej z jednego roku.

Przykładowe dane są dostępne w systemach demonstracyjnych zawierających zestaw danych demonstracyjnych firmy Contoso.

### <a name="role-and-permission-requirements"></a>Wymagania dotyczące roli i uprawnień

Zmiany zostaną wprowadzone w usługach Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps i Azure. Odpowiednie uprawnienia są wymagane we wszystkich tych środowiskach. Poniżej przedstawiono kilka przykładów zmian, które zostaną wprowadzone:

- W usłudze Microsoft Power Platform zostanie utworzone nowe środowisko.
- Na platformie Azure zostaną utworzone konto magazynu, magazyn kluczy i aplikacja.
- Administrator dzierżawy usługi Active Directory musi autoryzować dostęp aplikacji AI Builder do jeziora danych.
- Funkcja zostanie włączona w usłudze Dynamics 365.

Podczas wykonywania tego procesu będzie pomocna znajomość procesu tworzenia zasobów i zarządzania nimi w usługach Azure, Common Data Service i LCS.

## <a name="configure-finance-insights"></a>Konfigurowanie szczegółowych danych finansowych

Aby móc skorzystać z modułu Szczegółowe dane finansowe, musisz wykonać kilka kroków konfiguracyjnych. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania modułu Szczegółowe dane finansowe, zapoznaj się z tematem [Konfiguracja korzystania z modułu Finance Insights](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>Tworzenie projektu integratora danych

Należy utworzyć projekt integratora danych, tak aby dane wygenerowane przez model uczenia maszynowego mogły przepływać do rozwiązania Dynamics 365 Finance. Aby uzyskać informacje na temat procedury tworzenia tego projektu, należy zapoznać się z tematem [Tworzenie projektu integratora danych](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Włączanie funkcji modułu Szczegółowe dane finansowe

Po wykonaniu kroków konfiguracyjnych i skonfigurowaniu danych demonstracyjnych należy włączyć i skonfigurować każdą funkcję, która ma być używana: prognozy płatności od odbiorców, prognozowanie przepływów pieniężnych i propozycji budżetowych.

### <a name="enable-customer-payment-predictions"></a>Włączanie prognoz płatności odbiorcy
Jeśli do testowania prognoz płatności od odbiorców są używane dane demonstracyjne, może być konieczne zaimportowanie dodatkowych danych demonstracyjnych w celu pomyślnego utworzenia modelu AI. Aby się zapoznać z konkretnymi krokami importowania danych demonstracyjnych, zajrzyj do tematu [Konfigurowanie danych demonstracyjnych dla prognoz płatności](set-up-demo-data.md).

Aby włączyć prognozy płatności od odbiorców, należy wykonać procedurę tworzenia modelu uczenia maszynowego, który będzie używał danych organizacji do generowania prognoz dotyczących tego, kiedy odbiorcy prawdopodobnie zapłacą zaległe faktury oraz kiedy prawdopodobnie zostaną zapłacone konkretne faktury. Aby uzyskać więcej informacji i poznać dokładną procedurę, przeczytaj temat [Włączanie prognoz płatności odbiorcy](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Włączanie prognozowania przepływów pieniężnych
Aby włączyć prognozowanie przepływów pieniężnych, należy wykonać procedurę tworzenia modelu uczenia maszynowego, który będzie używał danych organizacji do generowania prognoz przepływów pieniężnych. Aby uzyskać więcej informacji i poznać dokładną procedurę, przeczytaj temat [Włączanie prognozowania przepływów pieniężnych](enable-cash-flow-forecasting.md). 

### <a name="set-up-and-use-cash-flow-forecasting"></a>Konfigurowanie i używanie funkcji prognozowania przepływów pieniężnych
Aby uzyskać informacje na temat konfigurowania i używania funkcji prognozowania przepływów pieniężnych, zobacz [Włączanie prognozowania przepływów pieniężnych](enable-cash-flow-forecasting.md). Więcej informacji na temat sposobu używania tej funkcji znajdziesz tutaj: [Prognozowanie przepływów pieniężnych](cash-flow-forecast-intro.md).

### <a name="enable-budget-proposals"></a>Włączanie propozycji budżetowych

Funkcja Propozycje budżetowe wykorzystuje model uczenia maszynowego i dane historyczne organizacji do generowania propozycji budżetowej. Wygenerowana propozycja może pomóc rozpocząć proces budżetowania, który jest efektywniejszy i sprawniejszy, niż proces ręczny. Aby zapoznać się ze szczegółową procedurą włączania tej funkcji, należy zapoznać się z tematem [Włączanie propozycji budżetowych](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Używanie funkcji modułu Szczegółowe dane finansowe

### <a name="using-customer-payment-predictions"></a>Korzystanie z prognoz płatności odbiorcy

Inteligentne prognozowanie przepływów pieniężnych bazuje na funkcjonalności prognozowania przepływów pieniężnych już istniejącej w rozwiązaniu Dynamics 365 Finance. Aby przejrzeć istniejące funkcje, zapoznaj się z tematem [Prognozowanie przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md).

- Aby się dowiedzieć, w jaki sposób prognozy płatności od odbiorców mogą dostarczać informacji potrzebnych do proaktywnego realizowania działań windykacyjnych, zobacz [Korzystanie z prognoz płatności odbiorcy](use-customer-payment-predictions.md).
- Aby uzyskać informacje pomocne w ocenie skuteczności modelu przewidywania po rozpoczęciu korzystania z tej funkcji, należy zapoznać się z tematem [Ocenianie modelu początkowych prognoz płatności odbiorcy](evaluate-payment-prediction.md).
- Aby uzyskać informacje pomocne w dostosowywaniu danych używanych do tworzenia prognoz i w ten sposób poprawić ich efektywność, należy zapoznać się z tematem [Usprawnij model przewidywania](improve-model.md).

Aby dowiedzieć się więcej o wynikach działania modeli przewidywania wykorzystujących sztuczną inteligencję, zobacz [Wyniki modeli uczenia maszynowego](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Korzystanie z prognoz przepływów pieniężnych

Funkcja Prognoza przepływów pieniężnych może pomóc dokładniej szacować stan środków pieniężnych. 

- Aby dowiedzieć się więcej o nowych funkcjach prognozowania przepływów pieniężnych, zobacz [Prognoza przepływów pieniężnych](cash-flow-forecast-intro.md).
- Aby uzyskać informacje o importowaniu zewnętrznych danych, które mają być uwzględnione w prognozie przepływów pieniężnych, zapoznaj się z tematami [Używanie danych zewnętrznych w prognozach przepływów pieniężnych](external-data-in-cash-flow.md). 
- Aby uzyskać informacje dotyczące korzystania z modelu AI w celu przewidywania długoterminowych przepływów środków pieniężnych, należy zapoznać się z tematem [Omówienie prognoz przepływów pieniężnych](cash-position.md).
- Aby uzyskać informacje dotyczące zapisywania stanu środków pieniężnych i prognoz przepływów pieniężnych jako migawek oraz porównywania migawek z wartościami rzeczywistymi, należy zapoznać się z tematem [Omówienie migawek](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Używanie propozycji budżetowej

Aby uzyskać informacje o przyspieszaniu tworzenia budżetu, zapoznaj się z tematem [Propozycje budżetowe](budget-proposals.md). 

Dane demonstracyjne propozycji budżetowych:

## <a name="feedback-and-support"></a>Opinie i pomoc techniczna

Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com).

## <a name="privacy-notice"></a>Klauzula prywatności

Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]