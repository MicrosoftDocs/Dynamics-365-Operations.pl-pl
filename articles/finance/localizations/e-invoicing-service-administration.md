---
title: Dodatkowe komponenty administracyjne do elektronicznego fakturowania
description: Ten temat zawiera informacje o składnikach związanych z administrowaniem dodatkiem Fakturowanie elektroniczne.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104425"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Dodatkowe komponenty administracyjne do elektronicznego fakturowania

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ten temat zawiera informacje o składnikach związanych z administrowaniem dodatkiem Fakturowanie elektroniczne. Zawiera również informacje o konfigurowaniu dodatku Fakturowanie elektroniczne.

## <a name="azure"></a>Azure

Użyj Microsoft Azure, aby utworzyć wpisy tajne dla magazynu kluczy i konta magazynu. Następnie użyj tej funkcji w konfiguracji dodatku Fakturowanie elektroniczne.

## <a name="lifecycle-services"></a>Usługa Lifecycle Services

Użyj Microsoft Dynamics Lifecycle Services (LCS), aby włączyć dodatek dla mikrousług dla projektu wdrożenia LCS.

W LCS wybierz kafelek **Zarządzanie funkcjami wersji zapoznawczej**, a następnie włącz funkcję **Usługi e-fakturowania**.

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) to interfejs używany do konfigurowania dodatku Fakturowanie elektroniczne. Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i hostowane w RCS. Gdy zasoby są gotowe, są publikowane w usłudze dodatkowej Fakturowanie elektroniczne.

Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md)

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Integracja z dodatkiem fakturowania elektronicznego

Zanim będziesz mógł używać RCS do konfigurowania faktur elektronicznych, musisz skonfigurować RCS, aby umożliwić komunikację z dodatkiem Fakturowanie elektroniczne. Tę konfigurację można ukończyć na karcie **Dodatek Fakturowanie elektroniczne** na stronie **Parametry raportowania elektronicznego**.

#### <a name="service-endpoint"></a>Punkt końcowy usługi

Adres URL punktu końcowego dodatku do fakturowania elektronicznego może się różnić w zależności od lokalizacji geograficznej centrum danych platformy Azure. W poniższej tabeli przedstawiono dostępność według regionów:

| Geografia centrum danych platformy Azure | Adres URL punktu końcowego usługi                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Wschodnie stany USA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| Zachodnie stany USA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| Europa Północna                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| Europa Zachodnia                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a>Identyfikator aplikacji

Identyfikator aplikacji jest identyfikatorem dodatku Fakturowanie elektroniczne. W tym przypadku wartość jest stała: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

#### <a name="lcs-environment-id"></a>Identyfikator środowiska LCS

Identyfikator środowiska LCS to identyfikator subskrypcji LCS Twojej organizacji.

### <a name="service-environments"></a>Środowiska usługi

Środowiska usług to partycje logiczne utworzone w celu obsługi funkcji fakturowania elektronicznego w dodatku Fakturowanie elektroniczne. Klucze tajne zabezpieczeń i certyfikaty cyfrowe oraz ład (czyli uprawnienia dostępu) należy skonfigurować na poziomie środowiska usługi.

Klienci mogą tworzyć dowolną liczbę środowisk usługowych. Wszystkie środowiska usług, które tworzy klient, są od siebie niezależne.

Środowiska usługowe muszą być tworzone i utrzymywane w RCS. Gdy środowiska usług są gotowe, należy je opublikować w dodatku Fakturowanie elektroniczne.

#### <a name="service-environment-status"></a>Stan środowiska usługi

Środowiskami usług można zarządzać za pomocą stanu. Dostępne są następujące opcje:

- **Nie opublikowano** — środowisko zostało utworzone, ale nie zostało jeszcze opublikowane.
- **Opublikowano** — środowisko zostało opublikowane w dodatku Fakturowanie elektroniczne.
- **Zmienione** — Atrybuty opublikowanego środowiska zostały zmienione, ale zmiany nie zostały jeszcze opublikowane.

#### <a name="customer-secrets"></a>Tajemnice odbiorców

Usługa dodatkowa Fakturowanie elektroniczne jest odpowiedzialna za przechowywanie wszystkich danych biznesowych w zasobach platformy Azure należących do Twojej firmy. Aby upewnić się, że usługa działa poprawnie i że wszystkie dane biznesowe, które są potrzebne i generowane przez dodatek Faktury elektroniczne, są dostępne tylko dla tego dodatku, musisz utworzyć dwa główne zasoby platformy Azure:

- Konto magazynu systemu Azure (magazyn obiektów BLOB) do przechowywania faktur elektronicznych
- Magazyn kluczy platformy Azure, w którym będą przechowywane certyfikaty i jednolity identyfikator zasobów (URI) konta magazynu

> [!NOTE]
> Dedykowany magazyn kluczy i konto magazynu klienta muszą być przydzielone specjalnie do użytku z dodatkiem Fakturowanie elektroniczne.

Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i magazyn kluczy](e-invoicing-create-azure-storage-account-key-vault.md).

#### <a name="users"></a>Użytkownicy

Każde środowisko usługowe musi zawierać listę użytkowników, którzy mogą łączyć się z Dynamics 365 Finance i Dynamics 365 Supply Chain Management w dodatku Fakturowanie elektroniczne.

#### <a name="publication"></a>Publikacja

Środowiska usług muszą zostać opublikowane w dodatku Fakturowanie elektroniczne, zanim będą mogły być używane. Finance i Supply Chain Management mają dostęp tylko do opublikowanych środowisk. Ponadto środowisko usługi musi zostać opublikowane, zanim jakiekolwiek aktualizacje jego atrybutów zaczną obowiązywać w usłudze fakturowania elektronicznego.

### <a name="connected-applications"></a>Połączone aplikacje

Połączone aplikacje to instancje Finance i Supply Chain Management, do których możesz chcieć dotrzeć za pośrednictwem RCS. Oprócz adresu URL aplikacji i jej dzierżawy, połączona aplikacja zawiera poświadczenia, które umożliwiają RCS łączenie się ze środowiskiem.

Za pomocą połączonych aplikacji można skonfigurować część funkcji fakturowania elektronicznego w rozwiązaniu Finance i Supply Chain Management, aby cała funkcja fakturowania elektronicznego działała.

## <a name="finance-and-supply-chain-management"></a>Finance i Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Integracja z dodatkiem fakturowania elektronicznego

Zanim będzie można używać programu Finance i Supply Chain Management do wystawiania faktur elektronicznych za pośrednictwem dodatku Fakturowanie elektroniczne, dodatek musi być skonfigurowany tak, aby umożliwić komunikację z usługą.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Funkcja integracji dodatku elektronicznego fakturowania

Aby umożliwić komunikację między rozwiązaniami Finance i Supply Chain Management a dodatkiem Fakturowanie elektroniczne, należy włączyć funkcję integracji dodatku **Fakturowanie elektroniczne** w obszarze roboczym **Zarządzanie funkcjami**.

#### <a name="service-endpoint"></a>Punkt końcowy usługi

Punkt końcowy usługi to adres URL, w którym znajduje się dodatek Fakturowanie elektroniczne. Przed wystawieniem faktur elektronicznych należy skonfigurować punkt końcowy usługi w programie Finance i Supply Chain Management, aby umożliwić komunikację z usługą.

Aby skonfigurować punkt końcowy usługi, przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametr dokumentu elektronicznego**, a następnie na zakładce **Usługi przesyłania** w polu **Adres URL dodatku do fakturowania elektronicznego** wprowadź adres URL zgodnie z opisem w tabeli opisanej w sekcji **Punkt końcowy usługi**.

#### <a name="environments"></a>Środowiska

Nazwa środowiska wprowadzona w Finance i Supply Chain Management odnosi się do nazwy środowiska utworzonego w RCS i opublikowanego w dodatku Fakturowanie elektroniczne.

Środowisko należy skonfigurować na karcie **Usługi przesyłania** na stronie **Parametrów dokumentu elektronicznego**, tak aby każde żądanie wystawienia faktury elektronicznej zawierało środowisko, w którym dodatek Fakturowanie elektroniczne może określić, która funkcja fakturowania elektronicznego musi przetworzyć żądanie.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Skonfiguruj faktury elektroniczne w RCS](e-invoicing-configuration-rcs.md)
- [Wystawiaj faktury elektroniczne w Finance i Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
