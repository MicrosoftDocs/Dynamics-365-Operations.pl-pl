---
title: Domeny w Dynamics 365 Commerce
description: W tym temacie opisano sposób obsługiwania domen w rozwiązaniach Microsoft Dynamics 365 Commerce.
author: BrShoo
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cb2b003168d32d05387bd45796d313736b11a41f
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517362"
---
# <a name="domains-in-dynamics-365-commerce"></a>Domeny w Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób obsługiwania domen w rozwiązaniach Microsoft Dynamics 365 Commerce.

Domeny są adresami sieci Web używanymi do nawigacji do witryn Dynamics 365 Commerce w przeglądarce sieciowej. Zarządzanie domeną można kontrolować za pomocą wybranego dostawcy DNS (Domain Name Server). Konstruktorzy witryn odwołują się domeny w ramach narzędzia tworzenia strony Dynamics 365 Commerce, aby koordynować, w jaki sposób witryna będzie dostępna po opublikowaniu. W tym temacie opisano sposób obsługi domen i odwoływanie się do nich w trakcie całego cyklu życia modułu tworzenia stron w Commerce i ich uruchamiania.

## <a name="provisioning-and-supported-host-names"></a>Konfiguracja i obsługiwane nazwy hostów

Podczas inicjowania obsługi środowiska handlu elektronicznego w [Microsoft Dynamics Lifecycle Services (usługi LCS)](https://lcs.dynamics.com/) pole **obsługiwane nazwy hostów** na ekranie obsługi technicznej handlu elektronicznego służy do wprowadzania domen, które zostaną skojarzone ze wdrożonym środowiskiem handlowym. Te domeny będą nazwami serwerów DNS dostępnymi dla odbiorcy, na których będą hostowane witryny platformy handlu elektronicznego. Wprowadzenie domeny na tym etapie nie powoduje ponownego przywrócenia ruchu domeny do Dynamics 365 Commerce. Ruch domeny będzie kierowany do punktu końcowego Commerce, gdy rekord DNS CNAME zostanie zaktualizowany w celu użycia punktu końcowego Commerce w domenie.

> [!NOTE]
> W polu **Obsługiwane nazwy hostów** można wprowadzić wiele domen, oddzielając je średnikami.

Na poniższej ilustracji przedstawiono ekran konfiguracji usługi handlu elektronicznego LCS z wyróżnionym polem **obsługiwane nazwy hostów**. 

![Ekran konfigurowania usługi LCS handlu elektronicznego z wyróżnionym polem **Obsługiwanych nazw hostów**](./media/Domains_ProvisioningeCommerceScreen.png)

Można utworzyć żądanie usługi w celu dodania dodatkowych domen do środowiska, jeśli już konfiguracja miała już miejsce. Aby utworzyć zlecenie usługi w ramach LCS, w środowisku należy przejść do **Pomocy technicznej \> Problemy** i wybrać opcję **Prześlij zdarzenie**.

## <a name="commerce-generated-urls"></a>Adresy URL wygenerowane przez Commerce

Podczas inicjowania obsługi Dynamics 365 Commerce środowiska handlu elektronicznego system Commerce wygeneruje adres URL, który będzie adresem roboczym środowiska. Do tego adresu URL odwołuje się łącze lokacji platformy handlu elektronicznego przedstawione w usłudze LCS po zainicjowaniu środowiska. Adres URL wygenerowany przez system Commerce jest zapisany w formacie `https://<e-commerce tenant name>.commerce.dynamics.com`, gdzie nazwą dzierżawy platformy jest nazwa wprowadzona w usłudze LCS dla środowiska Commerce.

Można również skorzystać z nazw hostów witryn produkcji w środowisku piaskownicy. Ta opcja jest idealna, jeśli witryna ma być kopiowana ze środowiska piaskownicy do produkcji.

## <a name="site-setup"></a>Ustawienia witryny

Po zainicjowaniu obsługi środowiska handlu elektronicznego należy skonfigurować witrynę w module konstruktora witryn Commerce, aby skojarzyć witrynę z roboczym adresem URL.

Podczas pierwszej konfiguracji witryny za pomocą konstruktora witryn zostanie wyświetlone okno dialogowe **Konfiguracja serwisu**.

Na poniższej ilustracji przedstawiono okno dialogowe **Konfigurowanie serwisu** dla witryny o nazwie „domyślna”, gdy dostęp do witryny jest uzyskiwany po raz pierwszy w konstruktorze witryn.

![Okno dialogowe **Konfigurowanie witryny**](./media/Domains_SetupyoursiteScreen.png)

Pole **Wybierz domenę** umożliwia skojarzenie jednej z obsługiwanych nazw hostów dostarczonych dla witryny w usłudze LCS do witryny w konstruktorze witryn.

Pole **Ścieżka** może pozostać puste lub można dodać dodatkowy ciąg ścieżki, który będzie widoczny w roboczym adresie URL. Pozostawienie pola **Ścieżka** pustym powiąże podstawowy adres URL wygenerowany przez system Commerce z witryną skonfigurowaną w konstruktorze witryn. Ścieżki muszą być unikatowe dla każdej pary lokacja/domena. W ramach wybranej lokacji i domeny tylko jeden oddział w środowisku może mieć pustą ścieżkę lub być skojarzony z ciągiem ścieżki unikatowej. Dowolny ciąg dodany do pola **Ścieżka** podczas konfigurowania witryny stanie się podścieżką do podstawowego wygenerowanego adresu URL, służącego do uzyskiwania dostępu do witryny w przeglądarce sieci Web.

> [!NOTE]
> Ścieżka jest również określana jako **Ścieżka dopasowania** podczas dodawania kanału w sekcji konfiguracji konstruktora witryn **Ustawienia witryny \> Kanały**.

Jeśli na przykład tworzysz witrynę w konstruktorze witryn o nazwie „Fabrikam” w dzierżawie o nazwie „XYZ” zostanie utworzona witryna z pustą ścieżką, a dostęp do opublikowanej zawartości witryny będzie można uzyskać w przeglądarce sieciowej, przechodząc bezpośrednio do podstawowego adresu URL wygenerowanego przez Commerce:

`https://xyz.commerce.dynamics.com`

Alternatywnie, jeśli dodano ścieżkę „Fabrikam” podczas konfiguracji tej samej witryny, można uzyskać dostęp do opublikowanej zawartości witryny w przeglądarce sieci Web przy użyciu następującego adresu URL:

`https://xyz.commerce.dynamics.com/fabrikam`

## <a name="pages-and-urls"></a>Strony i adresy URL

Po skonfigurowaniu witryny przy użyciu ścieżki wszystkie adresy URL skojarzone ze stronami w konstruktorze witryn zostaną skompilowane w ramach roboczego adresu URL (URL wygenerowanego przez system Commerce lub adresu URL wygenerowanego przez system Commerce wraz ze ścieżką) dla witryny. Tworzenie nowego adresu URL w module konstruktorze witryn (**URL /> + Nowa**) przez wybranie strony z listy w oknie dialogowym **Nowy adres URL** i wprowadzenie ścieżki URL do tej strony powoduje skojarzenie tego adresu URL z wybraną stroną. Następnie wartość ścieżki URL zostanie dołączona do roboczego adresu URL witryny w celu uzyskania dostępu do strony i jest oznaczona jako `./<URL path>` na liście adresów **URL** w konstruktorze witryn.

Na poniższej ilustracji przedstawiono okno dialogowe **Nowy adres URL** w konstruktorze witryn z wyróżnioną ścieżką URL. 

![**Nowy adres URL** — okno dialogowe w konstruktorze witryn](./media/Domains_PageSetup2a.png)

Na poniższej ilustracji przedstawiono okno dialogowe **URL** w konstruktorze witryn z wyróżnioną ścieżką URL na liście.

![Uruchom opcję przepływu użytkownika w przepływie zasad](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Domeny w konstruktorze witryn

Obsługiwane wartości nazw hostów są dostępne do skojarzenia z domeną podczas konfigurowania witryny. W przypadku wybrania obsługiwanej wartości nazwy hosta jako domeny zostanie wyświetlona nazwa wybranej domeny, której używać będzie konstruktor witryn. Ta domena jest tylko odwołaniem w środowisku Commerce, więc ruch na żywo dla tej domeny nie będzie jeszcze przekazywany do Dynamics 365 Commerce.

Jeśli skonfigurowano dwie witryny z dwiema różnymi domenami, podczas pracy w konstruktorze witryn można dołączyć atrybut **?domain=** do funkcjonującego adresu URL, aby uzyskać dostęp do opublikowanej zawartości witryny w przeglądarce.

Na przykład środowisko „xyz” zostało skonfigurowane i utworzono i skojarzono z nim dwie witryny: jedną z domeną `www.fabrikam.com`, a drugą z domeną `www.constoso.com`. Każda witryna została skonfigurowana przy użyciu pustej ścieżki. W przeglądarce sieci Web można uzyskać dostęp do tych dwóch witryn, korzystając z atrybutu **?domain=**:
- `https://xyz.commerce.dynamics.com?domain=www.fabrikam.com`
- `https://xyz.commerce.dynamics.com?domain=www.contoso.com`

Jeśli ciąg kwerendy domeny nie jest podany w środowisku z podanymi wieloma domenami, w systemie Commerce zostanie użyta pierwsza z nich. Jeśli na przykład podczas konfigurowania witryny została podana ścieżka „fabrikam”, adres URL `https://xyz.commerce.dynamics.com` może zostać użyty do uzyskania dostępu do opublikowanej zawartości witryny `www.fabrikam.com`.

## <a name="traffic-forwarding-in-production"></a>Przekazywanie ruchu w produkcji

Istnieje możliwość symulowania wielu domen za pomocą parametrów kwerendy domeny w samym punkcie końcowym commerce.dynamics.com. Jeśli jednak konieczne jest przechodzenie do trybu produkcji, należy przesłać dalej ruch dla domeny niestandardowej do punktu końcowego `<e-commerce tenant name>.commerce.dynamics.com`.

Punkt końcowy `<e-commerce tenant name>.commerce.dynamics.com` nie obsługuje niestandardowych warstw sieci Secure Sockets Layer (SSLs), więc domeny niestandardowe należy skonfigurować przy użyciu usługi front door service lub sieci CDN. 

Aby skonfigurować domeny niestandardowe przy użyciu usługi front door service lub sieci CDN, dostępne są dwie opcje:

- Skonfiguruj usługę front door service, taką jak np. Azure Front Door, aby obsługiwać ruch przód-tył i łączyć się ze środowiskiem Commerce. Pozwala to na większą kontrolę nad zarządzaniem domenami i certyfikatami oraz bardziej szczegółowe zasady zabezpieczeń.
- Należy skorzystać z dostarczonej przez Commerce instancji Azure Front Door. Wymaga to koordynacji działania z zespołem Dynamics 365 Commerce w zakresie weryfikacji domeny i uzyskiwania certyfikatów SSL dla domeny produkcji.

Aby uzyskać informacje o tym, jak skonfigurować usługę CDN bezpośrednio, należy zapoznać się z tematem [Dodawanie obsługi sieci dostarczania zawartości (CDN)](add-cdn-support.md).

Aby można było skorzystać z oferowanej przez Commerce instancji Azure Front Door należy utworzyć żądanie usługi pomocy dotyczącej konfiguracji sieci CDN od zespołu wdrażania Commerce. 

- Należy podać nazwę firmy, domenę produkcyjną, identyfikator środowiska oraz nazwę dzierżawcy produkcji platformy handlu elektronicznego. 
- Należy potwierdzić, czy jest to domena istniejąca (używana w aktualnie aktywnej witrynie) lub nowa. 
- W przypadku nowej domeny można zrealizować weryfikację domeny i certyfikat SSL w jednym kroku. 
- W przypadku domeny obsługującej istniejącą witrynę sieciową, do przeprowadzenia weryfikacji domeny i certyfikatu SSL wykorzystywany jest proces wieloetapowy. Proces ten obejmuje podpisanie co najmniej 7-dniowej umowy dotyczącej poziomu usług (SLA) dla domeny, ponieważ praca obejmuje wiele kolejnych etapów.

Aby utworzyć zlecenie usługi w ramach LCS, w środowisku należy przejść do **Pomocy technicznej \> Problemy** i wybrać opcję **Prześlij zdarzenie**.

> [!NOTE]
> Domeny niestandardowe z protokołem SSL są obsługiwane tylko w środowiskach produkcyjnych. W środowiskach nieprodukcyjnych, takich jak piaskownica i testowanie akceptacji użytkownika (UAT), w przeglądarce sieci Web należy wykorzystać adres URL wygenerowany przez Commerce.

## <a name="ssl-certificate-process"></a>Proces certyfikatu SSL

W przypadku zgłoszenia zlecenia serwisowego zespół ds. Commerce będzie koordynował następujące kroki z użytkownikiem.

Dla nowych domen:
- Zespół ds. Commerce skonfiguruje wystąpienie Azure Front Door (hostowane przez Commerce).
- Następnie zespół Commerce przekaże rekord CNAME do wskazywania domeny niestandardowej.
- Po zaktualizowaniu rekordu CNAME wystąpienie Azure Front Door hostowane przez Commerce będzie mogło zweryfikować własność domeny i uzyskać certyfikat SSL.

Dla domen istniejących/aktywnych:
- Zespół Commerce przedstawi instrukcje dodania rekordu CNAME `afdverify.<custom-domain>` w celu dostarczenia go dostawcy DNS domeny.
- Po zakończeniu pracy zespół Commerce doda domenę do wystąpienia Azure Front Door i udostępni dodatkowe rekordy DNS TXT do dodania do systemu DNS domeny.
- Po zakończeniu rekordów TXT zespół Commerce ukończy aktualizacje Azure Front Door dla domeny, która skonfiguruje certyfikat SSL.

## <a name="apex-domains"></a>Domeny Apex

Wystąpienie Azure Front Door dostarczone wraz z Commerce nie obsługuje domen Apex (domen głównych, które nie zawierają poddomen). Domeny Apex wymagają adresu IP do rozwiązania, a wystąpienie Azure Front Door istnieje tylko wraz z wirtualnymi punktami końcowymi. Aby skorzystać z domeny Apex, dostępne są dwie opcje:

- **Opcja 1** — aby przekierować domenę Apex do domeny „www”, należy skorzystać z dostawcy DNS. Na przykład fabrikam.com przekierowuje do `www.fabrikam.com`, gdzie `www.fabrikam.com` to rekord CNAME wskazujący na hostowane przez Commerce wystąpienie Azure Front Door.

- **Opcja 2** — skonfigurowanie swojego wystąpienia sieci CDN/front-door samemu w taki sposób, aby obsługiwać domenę Apex.

> [!NOTE]
> Jeśli korzystasz z Azure Front Door, musisz również skonfigurować usługę DNS w tej samej subskrypcji. Domena Apex obsługiwana przez usługę Azure DNS może wskazywać na Azure Front Door jako na rekord aliasu. Jest to tylko obejście problemu, ponieważ domeny Apex muszą zawsze wskazywać adres IP.

  ## <a name="additional-resources"></a>Dodatkowe zasoby

  [Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

  [Konfigurowanie kanału sklepu internetowego](online-stores.md)

  [Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

  [Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

  [Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

  [Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

  [Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

  [Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

  [Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

  [Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

  [Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
