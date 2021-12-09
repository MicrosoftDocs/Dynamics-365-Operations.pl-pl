---
title: Finance Insights — strona główna
description: Moduł Szczegółowe dane finansowe udostępnia konfigurowalne i rozszerzalne modele, które pomagają dokładnie i inteligentnie przewidywać przepływy pieniężne w firmie, prognozować terminy otrzymania płatności za zaległe należności oraz generować propozycje budżetowe, które mogą przyspieszyć proces budżetowania. Wszystkie te funkcje są oparte na inteligentnych modelach uczenia maszynowego.
author: ShivamPandey-msft
ms.date: 11/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: dfc4d9cb5be4d8d287122fd33bf09b0570498169
ms.sourcegitcommit: a46f0bf9f58f559bbb2fa3d713ad86875770ed59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813754"
---
# <a name="finance-insights-home-page"></a>Finance Insights — strona główna

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Moduł Finance insights udostępnia konfigurowalne i rozszerzalne rozwiązania, które pomagają inteligentnie przewidywać przepływy pieniężne w firmie, prognozować terminy otrzymania płatności za zaległe należności oraz generować propozycje budżetowe, które pomagają przyspieszyć proces budżetowania. Te funkcje używają inteligentnych szablonów uczenia maszynowego do tworzenia modeli przy użyciu danych dostarczanych przez użytkownika (w tym danych od innej firmy, takich jak informacje o raportach klientów z biura). Te inteligentne możliwości informowania o procesach podejmowania decyzji pomagają w podjęciu skutecznego działania w reakcji na bieżącą i przewidzianą sytuację biznesową. Użytkownik jest odpowiedzialny za wszelkie dane używane w aplikacji Finance Insights lub za ich dane wyjściowe.

> [!NOTE]
> Aplikacja Finance insights w wersji zapoznawczej jest dostępna do wdrożenia w Stanach Zjednoczonych Ameryki, Kanadzie, Wielkiej Brytanii, Europie, Japonii, Azji i Pacyfiku, Australii i Nowej Zelandii. Firma Microsoft stopniowo zwiększa obsługę wielu regionów.

## <a name="prerequisites"></a>Wymagania wstępne

Ta sekcja zawiera listę wymagań dotyczących korzystania z modułu Szczegółowe dane finansowe. Tam, gdzie to możliwe, udostępniono łącza do źródeł dodatkowych informacji.

### <a name="legal-requirements"></a>Wymagania prawne

Aby zawnioskować o udział w programie zapoznawczym, wypełnij [umowę na korzystanie z wersji zapoznawczej modułu Szczegółowe dane finansowe w rozwiązaniu Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u)

### <a name="system-requirements"></a>Wymagania systemowe

Do korzystania z wersji zapoznawczej modułu Szczegółowe dane Finance jest wymagane środowisko warstwy 2 (wielostanowiskowe). Aby uzyskać informacje kontekstowe o środowiskach, należy zapoznać się z tematem [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Wymagania dotyczące wersji

Ten temat dotyczy rozwiązania Microsoft Dynamics 365 Finance w wersji 10.0.21 lub nowszej.

### <a name="historical-data-requirements"></a>Wymagania dotyczące danych historycznych

Do poprawnego wytrenowania modelu uczenia maszynowego, który jest używany przez funkcję prognozowania płatności od odbiorców, są potrzebne faktury od odbiorców co najmniej z jednego roku. Dla prognoz przepływów pieniężnych zaleca się trzy lata danych historycznych. Dla inteligentnych propozycji budżetu zalecane są trzy lata budżetu historycznego i/lub wartości rzeczywistych.

## <a name="configure-finance-insights"></a>Konfigurowanie rozwiązania Finance Insights

Aby móc skorzystać z modułu Finance insights, musisz wykonać kilka kroków konfiguracyjnych. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania modułu Szczegółowe dane finansowe, zapoznaj się z tematem [Konfiguracja korzystania z modułu Finance Insights](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>Tworzenie projektu integratora danych

Należy utworzyć projekt integratora danych, tak aby dane wygenerowane przez model uczenia maszynowego mogły przepływać do rozwiązania Dynamics 365 Finance. Aby uzyskać informacje na temat procedury tworzenia tego projektu, należy zapoznać się z tematem [Tworzenie projektu integratora danych](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Włączanie funkcji modułu Szczegółowe dane finansowe

Po wykonaniu kroków konfiguracyjnych i skonfigurowaniu danych demonstracyjnych należy włączyć i skonfigurować każdą funkcję, która ma być używana: prognozy płatności od odbiorców, prognozowanie przepływów pieniężnych i propozycji budżetowych.

### <a name="enable-customer-payment-predictions"></a>Włączanie prognoz płatności odbiorcy
Jeśli do testowania prognoz płatności od odbiorców są używane dane demonstracyjne, może być konieczne zaimportowanie dodatkowych danych demonstracyjnych w celu pomyślnego utworzenia modelu AI. 

Aby włączyć prognozy płatności od odbiorców, należy wykonać procedurę tworzenia modelu uczenia maszynowego, który będzie używał danych do generowania prognoz dotyczących tego, kiedy odbiorcy prawdopodobnie zapłacą zaległe faktury oraz kiedy prawdopodobnie zostaną zapłacone konkretne faktury. Aby uzyskać więcej informacji i poznać dokładną procedurę, przeczytaj temat [Włączanie prognoz płatności odbiorcy](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Włączanie prognozowania przepływów pieniężnych
Aby umożliwić prognozowanie przepływów pieniężnych, należy wykonać szereg kroków w celu zbudowania modelu uczenia maszynowego, który wykorzystuje dane organizacji do generowania prognoz przepływów pieniężnych. Aby uzyskać więcej informacji i poznać dokładną procedurę, przeczytaj temat [Włączanie prognozowania przepływów pieniężnych](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Włączanie propozycji budżetowych

Funkcja Propozycje budżetowe wykorzystuje model uczenia maszynowego i dane historyczne organizacji do generowania propozycji budżetowej. Wygenerowana propozycja może pomóc rozpocząć proces budżetowania, który jest efektywniejszy i sprawniejszy, niż proces ręczny. Aby zapoznać się ze szczegółową procedurą włączania tej funkcji, należy zapoznać się z tematem [Włączanie propozycji budżetowych](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Używanie funkcji modułu Szczegółowe dane finansowe

### <a name="using-customer-payment-predictions"></a>Korzystanie z prognoz płatności odbiorcy

- Aby dowiedzieć się, w jaki sposób prognozy płatności Klienta mogą dostarczać informacji wymaganych do proaktywnego rozpoczęcia działań windykacyjnych, zobacz [Korzystanie z prognoz płatności odbiorcy](use-customer-payment-predictions.md).
- Aby uzyskać informacje pomocne w ocenie skuteczności modelu przewidywania po rozpoczęciu korzystania z tej funkcji, należy zapoznać się z tematem [Ocenianie modelu początkowych prognoz płatności odbiorcy](evaluate-payment-prediction.md).
- Aby uzyskać informacje pomocne w dostosowywaniu danych używanych do tworzenia prognoz i w ten sposób poprawić ich efektywność, należy zapoznać się z tematem [Usprawnij model przewidywania](improve-model.md).
- Aby dowiedzieć się więcej o wynikach działania modeli przewidywania wykorzystujących sztuczną inteligencję, zobacz [Wyniki modeli uczenia maszynowego](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Korzystanie z prognoz przepływów pieniężnych

Funkcja Prognoza przepływów pieniężnych może pomóc dokładniej szacować stan środków pieniężnych. Inteligentne prognozowanie przepływów pieniężnych bazuje na funkcjonalności prognozowania przepływów pieniężnych już istniejącej w rozwiązaniu Dynamics 365 Finance. Aby przejrzeć istniejące funkcje, zapoznaj się z tematem [Prognozowanie przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md).

- Aby dowiedzieć się więcej o nowych funkcjach prognozowania przepływów pieniężnych, zobacz [Prognoza przepływów pieniężnych](cash-flow-forecast-intro.md).
- Aby uzyskać informacje o importowaniu zewnętrznych danych, które mają być uwzględnione w prognozie przepływów pieniężnych, zapoznaj się z tematami [Używanie danych zewnętrznych w prognozach przepływów pieniężnych](external-data-in-cash-flow.md). 
- Aby uzyskać informacje dotyczące korzystania z modelu AI w celu przewidywania krótkoterminowych przepływów środków pieniężnych, należy zapoznać się z tematem [Omówienie stanu środków pieniężnych](cash-position.md).
- Aby uzyskać informacje dotyczące zapisywania stanu środków pieniężnych i prognoz przepływów pieniężnych jako migawek oraz porównywania migawek z wartościami rzeczywistymi, należy zapoznać się z tematem [Omówienie migawek](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Używanie propozycji budżetowej

Aby uzyskać informacje o przyspieszaniu tworzenia budżetu, zapoznaj się z tematem [Propozycje budżetowe](budget-proposals.md). 

## <a name="feedback-and-support"></a>Opinie i pomoc techniczna

Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Finance Insights](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
