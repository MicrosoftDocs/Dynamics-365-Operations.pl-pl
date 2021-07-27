---
title: Wyszukiwanie formatów rozszerzonych raportów elektronicznych (ER)
description: W tym temacie opisano sposób, w jaki można skonfigurować odwołanie do formatu ER w sekcji Wyszukiwanie formatu ER, gdy wymagany format jest przechowywany w repozytorium globalnym.
author: NickSelin
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: baba699a1b8efc986b4b274b8faf143d24d69e96
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355788"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>Zezwalaj użytkownikom na konfigurowanie odwołania do formatu modelu konfiguracji z repozytorium globalnego

[!include [banner](../includes/banner.md)]

Można użyć narzędzia [Raportowanie elektroniczne](general-electronic-reporting.md) (ER) do konfigurowania [formatów](general-electronic-reporting.md#FormatComponentOutbound) dokumentów elektronicznych zgodnie z wymogami prawnymi obowiązującymi w różnych krajach/regionach. Można również używać struktury ER do konfiguracji [formatów](general-electronic-reporting.md#FormatComponentInbound), aby skonfigurować formaty do analizowania dokumentów przychodzących i używać informacji z tych dokumentów do dołączania lub aktualizowania danych aplikacji. Każdy z tych formatów może być używany w instancji Dynamics 365 Finance do obsługi przychodzących lub wychodzących dokumentów biznesowych w ramach pewnego procesu biznesowego.

Zazwyczaj należy określić, jaki format ER musi być używany w pewnym procesie biznesowym. W tym celu należy wybrać jeden format ER w polu wyszukiwania, które jest skonfigurowane jako część parametrów specyficznych dla procesu biznesowego. Te pola odnośników są zwykle implementowane przy użyciu odpowiedniego interfejsu API struktury ER systemu. Aby uzyskać więcej informacji, należy zapoznać się z [kodem interfejsu API programu ER w celu wyświetlenia wyszukiwania mapowania formatu](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

Na przykład podczas konfigurowania [parametrów handlu zagranicznego](../../../finance/localizations/emea-intrastat.md#set-up-foreign-trade-parameters), należy skonfigurować odwołania do poszczególnych formatów ER, które będą używane do generowania deklaracji Intrastat i raportu kontroli deklaracji Intrastat. Poniższe zrzuty ekranu pokazują, w jaki sposób ma wyglądać pole wyszukiwania formatów ER na stronie **parametry handlu zagranicznego**.

Jeśli bieżące wystąpienie Finance nie zawiera żadnych formatów skojarzonych z procesami biznesowymi Intrastat, to pole odnośnika będzie puste.

[![Strona parametrów handlu zagranicznego.](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Jeśli bieżące wystąpienie Finance zawiera formaty skojarzone z procesami biznesowymi Intrastat, to pole odnośnika będzie wypełnione formatami ER.

[![Strona parametrów handlu zagranicznego.](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

To wyszukiwanie oferuje tylko formaty ER, które zostały już zaimportowane do bieżącego wystąpienia Finance. Aby [zaimportować](./tasks/er-import-configuration-lifecycle-services.md) rozwiązania ER do bieżącego wystąpienia Finance, trzeba mieć uprawnienia do uruchamiania odpowiedniej funkcji systemu, która obsługuje [cykle trwania](general-electronic-reporting-manage-configuration-lifecycle.md) rozwiązań ER, które zawierają formaty ER.

Począwszy od wersji finansowej 10.0.9 (wydanie z kwietnia 2020) interfejs użytkownika w wyszukiwaniu formatu ER, który jest implementowany przy użyciu interfejsu API środowiska ER Framework, został rozszerzony. Nadal można wybrać istniejące formaty ER, które są dostępne w skróconej karcie **Wyboru konfiguracji formatu**. Oprócz tego wyszukiwanie rozszerzone umożliwia nowe opcje wyszukiwania w repozytorium globalnym (GR) w celu znalezienia konkretnych formatów ER. Wszystkie formaty ER dla GR są oferowane podczas **Importu z repozytorium globalnego** na skróconej karcie.

[![Strona parametrów handlu zagranicznego.](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

Podobnie jak na skróconej karcie **Wyboru konfiguracji formatu**, skrócona karta **Import z repozytorium globalnego** zawiera tylko te formaty ER, które są stosowane do procesu biznesowego, dla którego w polu wyszukiwania wybrano format ER. W tym przykładzie wygenerowanie deklaracji Intrastat. Format ER jest odpowiedni dla firmy, do której użytkownik jest aktualnie zalogowany, w zależności od kontekstu kraju firmy.

Po wybraniu formatu ER z **Importowanego z repozytorium globalnego** na skróconej karcie, wybrana [konfiguracja](general-electronic-reporting.md#Configuration) formatu ER jest importowana z pola GR do bieżącego wystąpienia Finance.

[![Strona parametrów handlu zagranicznego.](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Następnie, jeśli import zakończy się pomyślnie, odwołanie do importowanego formatu ER będzie przechowywane w tym polu wyszukiwania. Przy pierwszym korzystaniu z pola GR należy skorzystać z podanego łącza, aby zarejestrować [Regulatory Configuration Service](https://aka.ms/rcs), która jest używana do zarządzania dostępem do magazynu GR.

[![Strona parametrów handlu zagranicznego.](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Domyślnie, **Import z repozytorium globalnego** na skróconej karcie prezentuje listę formatów ER z magazynu tymczasowego, który jest automatycznie tworzony na podstawie zawartości GR na potrzeby ulepszeń wydajności. Dzieje się tak, gdy **Import z repozytorium globalnego** na skróconej karcie jest otwierany po raz pierwszy, co może potrwać kilka sekund.

Jeśli nie widzisz wymaganego formatu ER w opcji **Import z repozytorium globalnego** na skróconej karcie, ale masz pewność, że ten format jest przechowywany w polu GR, wybierz opcję **Synchronizuj**. Ta opcja spowoduje aktualizację magazynu tymczasowego i zsynchronizowanie go z bieżącą zawartością GR.

## <a name="feature-activation"></a>Aktywacja funkcji

Dostępność tej funkcjonalności jest kontrolowana przez funkcję **rozszerzonego wyszukiwania konfiguracji formatu ER umożliwiająca wysyłanie zapytań dotyczących globalnego repozytorium** w module **Zarządzanie funkcjami**. Ten funkcjonalność jest włączona domyślnie.

[![Strona dot. zarządzania funkcjami.](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Zagadnienia dotyczące zabezpieczeń

Uprawnienie **Obsługa repozytoriów konfiguracji** (**ERMaintainSolutionRepositories**) steruje dostępem do pola GR dla użytkownika otwierającego wyszukiwanie formatu ER z włączoną opcją **Import z globalnego repozytorium** na skróconej karcie. Aby umożliwić użytkownikom dostęp do zawartości GR na podstawie wyszukiwań w formacie ER, należy zmienić ustawienia zabezpieczeń, przyznając uprawnienie **ERMaintainSolutionRepositories** użytkownikom bezpośrednio lub za pomocą przypisanych wcześniej ról i obowiązków.

Poniższy zrzut pokazuje, jak to uprawnienie może być przyznane użytkownikom, którzy są przypisani do roli **księgowej**. Dzięki tej roli użytkownicy mogą konfigurować parametry handlu zagranicznego i konfigurować odwołania do formatów ER w polach **Mapowanie formatów plików** i **Raport formatów mapowania** na stronie **Parametry handlu zagranicznego**.

[![Strona konfiguracji zabezpieczeń.](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Ograniczenia

Dostęp do pola GR w wyszukiwaniu formatu ER jest obecnie obsługiwany tylko w przypadku wybrania formatu ER, który jest używany do generowania dokumentów wychodzących.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>Dlaczego nie można uzyskać dostępu do globalnego repozytorium z poziomu wyszukiwania formatu ER?

Jeśli zostało włączone **Rozszerzone wyszukiwanie konfiguracji formatu ER, zezwalające na wysyłanie zapytań do repozytorium globalnego** na stronie **Zarządzanie funkcjami**, ale użytkownicy nie będą mogli wyświetlać formatów ER na skróconej karcie **Imporcie z repozytorium globalnego**, a opcja **Synchronizacji** jest widoczna, ale wyłączona, upewnij się, że udzielono użytkownikowi uprawnienia **Obsługa repozytoriów konfiguracji** (**ERMaintainSolutionRepositories**). Skontaktuj się z administratorem systemu, aby uzyskać to uprawnienie.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Struktura API raportowania elektronicznego ER](er-apis-app73.md)
- [Zarządzanie cyklem życia konfiguracji raportowania elektronicznego (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]