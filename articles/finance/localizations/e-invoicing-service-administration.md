---
title: Składniki administracyjne fakturowania elektronicznego
description: Ten temat zawiera informacje o składnikach związanych z administrowaniem Fakturowaniem elektronicznym.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3ac4a03d75898680b5655421f3024dc6f666464c
ms.sourcegitcommit: 54d3ec0c006bfa9d2b849590205be08551c4e0f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/30/2021
ms.locfileid: "5963198"
---
# <a name="electronic-invoicing-administration-components"></a>Składniki administracyjne fakturowania elektronicznego

[!include [banner](../includes/banner.md)]


Ten temat zawiera informacje o składnikach związanych z administrowaniem Fakturowaniem elektronicznym. Zawiera również informacje o konfigurowaniu usługi Fakturowanie elektroniczne.

## <a name="azure"></a>Azure

Użyj Microsoft Azure, aby utworzyć wpisy tajne dla Key Vault i konta magazynu. Następnie użyj tej funkcji w konfiguracji funkcji Fakturowanie elektroniczne.

## <a name="lifecycle-services"></a>Usługa Lifecycle Services

Użyj Microsoft Dynamics Lifecycle Services (LCS), aby włączyć funkcję dla mikrousług dla projektu wdrożenia LCS.

> [!NOTE]
> Instalacja mikrousługi w umacie LCS wymaga co najmniej maszyny wirtualnej warstwy 2. Aby uzyskać więcej informacji o planowaniu w środowiskach, należy zapoznać się z tematem [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) to interfejs używany do konfigurowania Fakturowania elektronicznego. Zasoby takie jak środowiska i funkcje fakturowania elektronicznego są tworzone, utrzymywane i hostowane w RCS. Gdy zasoby są gotowe, są publikowane w usłudze Fakturowanie elektroniczne.

Aby uzyskać informacje o rejestracji w RCS, zobacz temat [Regulatory services](https://marketing.configure.global.dynamics.com/).

Aby uzyskać więcej informacji na temat RCS, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md)

### <a name="integration-with-electronic-invoicing"></a>Integracja z funkcją fakturowania elektronicznego 

Zanim będziesz mógł używać RCS do konfigurowania faktur elektronicznych, musisz skonfigurować RCS, aby umożliwić komunikację z funkcją Fakturowanie elektroniczne. Tę konfigurację można ukończyć na karcie **Fakturowanie elektroniczne** na stronie **Parametry raportowania elektronicznego**.

#### <a name="service-endpoint"></a>Punkt końcowy usługi

Fakturowanie elektroniczne jest dostępne w kilku lokalizacjach geograficznych centrów danych platformy Azure. W poniższej tabeli przedstawiono dostępność według regionów.

| Geografia centrum danych platformy Azure |
|----------------------------|
| Wschodnie stany USA                    |
| Zachodnie stany USA                    |
| Europa Północna                   |
| Europa Zachodnia                    |

### <a name="service-environments"></a>Środowiska usługi

Środowiska usług to partycje logiczne utworzone w celu obsługi funkcji fakturowania elektronicznego w Fakturowaniu elektronicznym. Klucze tajne zabezpieczeń i certyfikaty cyfrowe oraz ład (czyli uprawnienia dostępu) należy skonfigurować na poziomie środowiska usługi.

Klienci mogą tworzyć dowolną liczbę środowisk usługowych. Wszystkie środowiska usług, które tworzy klient, są od siebie niezależne.

Środowiska usługowe muszą być tworzone i utrzymywane w RCS. Gdy środowiska usług są gotowe, należy je opublikować w funkcji Fakturowanie elektroniczne.

#### <a name="service-environment-status"></a>Stan środowiska usługi

Środowiskami usług można zarządzać za pomocą stanu. Dostępne są następujące opcje:

- **Nie opublikowano** — środowisko zostało utworzone, ale nie zostało jeszcze opublikowane.
- **Opublikowano** — środowisko zostało opublikowane w funkcji Fakturowanie elektroniczne.
- **Zmienione** — Atrybuty opublikowanego środowiska zostały zmienione, ale zmiany nie zostały jeszcze opublikowane.

#### <a name="customer-secrets"></a>Tajemnice odbiorców

Usługa Fakturowanie elektroniczne jest odpowiedzialna za przechowywanie wszystkich danych biznesowych w zasobach platformy Azure należących do Twojej firmy. Aby upewnić się, że usługa działa poprawnie i że wszystkie dane biznesowe, które są potrzebne i generowane przez Faktury elektroniczne, są dostępne tylko dla tego dodatku, musisz utworzyć dwa główne zasoby platformy Azure:

- Konto magazynu systemu Azure (magazyn obiektów BLOB) do przechowywania faktur elektronicznych
- Magazyn Azure Key Vault, w którym będą przechowywane certyfikaty i jednolity identyfikator zasobów (URI) konta magazynu


Dedykowany magazyn Key Vault i konto magazynu klienta muszą być przydzielone specjalnie do użytku z Fakturowaniem elektronicznym. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu Azure i Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

Aby monitorować kondycję magazynu Key Vault i odbierać alerty, skonfiguruj monitor Azure dla magazynu Key Vault. Włączenie rejestrowania magazynu Key Vault umożliwia monitorowanie, jak, kiedy i kto uzyskuje dostęp do magazynów Key Vault. Aby uzyskać więcej informacji, zobacz temat [Monitorowanie i alerty Azure Key Vault](/azure/key-vault/general/alert) i [Włączanie rejestrowania magazynu Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).

Dobrą praktyką jest rotacja wpisów tajnych. Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją wpisów tajnych](/azure/key-vault/secrets/).

#### <a name="users"></a>Użytkownicy

Każde środowisko usługowe musi zawierać listę użytkowników, którzy mogą łączyć się z Dynamics 365 Finance i Dynamics 365 Supply Chain Management w funkcji Fakturowanie elektroniczne.

#### <a name="publication"></a>Publikacja

Środowiska usług muszą zostać opublikowane w funkcji Fakturowanie elektroniczne, zanim będą mogły być używane. Finance i Supply Chain Management mają dostęp tylko do opublikowanych środowisk. Ponadto środowisko usługi musi zostać opublikowane, zanim jakiekolwiek aktualizacje jego atrybutów zaczną obowiązywać w usłudze fakturowania elektronicznego.

### <a name="connected-applications"></a>Połączone aplikacje

Połączone aplikacje to instancje Finance i Supply Chain Management, do których możesz chcieć dotrzeć za pośrednictwem RCS. Oprócz adresu URL aplikacji i jej dzierżawy, połączona aplikacja zawiera poświadczenia, które umożliwiają RCS łączenie się ze środowiskiem.

Za pomocą połączonych aplikacji można skonfigurować część funkcji fakturowania elektronicznego w rozwiązaniu Finance i Supply Chain Management, aby cała funkcja fakturowania elektronicznego działała.

## <a name="finance-and-supply-chain-management"></a>Finance i Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Integracja z funkcją fakturowania elektronicznego

Zanim będzie można używać programu Finance i Supply Chain Management do wystawiania faktur elektronicznych za pośrednictwem Fakturowania elektronicznego, dodatek musi być skonfigurowany tak, aby umożliwić komunikację z usługą.

#### <a name="electronic-invoicing-integration-feature"></a>Funkcja integracji fakturowania elektronicznego

Aby umożliwić komunikację między rozwiązaniami Finance i Supply Chain Management a dodatkiem Fakturowanie elektroniczne, należy włączyć funkcję integracji **Fakturowanie elektroniczne** w obszarze roboczym **Zarządzanie funkcjami**.

#### <a name="service-endpoint"></a>Punkt końcowy usługi

Punkt końcowy usługi to adres URL, w którym znajduje się Fakturowanie elektroniczne. Przed wystawieniem faktur elektronicznych należy skonfigurować punkt końcowy usługi w programie Finance i Supply Chain Management, aby umożliwić komunikację z usługą.

Aby skonfigurować punkt końcowy usługi, przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametr dokumentu elektronicznego**, a następnie na zakładce **Usługi przesyłania** w polu **Adres URL do fakturowania elektronicznego** wprowadź adres URL zgodnie z opisem w tabeli opisanej w sekcji **Punkt końcowy usługi**.

#### <a name="environments"></a>Środowiska

Nazwa środowiska wprowadzona w Finance i Supply Chain Management odnosi się do nazwy środowiska utworzonego w RCS i opublikowanego w Fakturowaniu elektronicznym.

Środowisko należy skonfigurować na karcie **Usługi przesyłania** na stronie **Parametrów dokumentu elektronicznego**, tak aby każde żądanie wystawienia faktury elektronicznej zawierało środowisko, w którym Fakturowanie elektroniczne może określić, która funkcja fakturowania elektronicznego musi przetworzyć żądanie.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Skonfiguruj faktury elektroniczne w RCS](e-invoicing-configuration-rcs.md)
- [Wystawiaj faktury elektroniczne w Finance i Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
