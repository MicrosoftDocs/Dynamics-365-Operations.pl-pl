---
title: "Konfigurowanie i wdrażanie środowisk lokalnych"
description: "Ten temat zawiera informacje na temat planowania, konfigurowania i wdrażania środowiska lokalnego."
author: kfend
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 3e9a2e33d9579769f6808b598f865d75f072c450
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>Konfigurowanie i wdrażanie środowisk lokalnych

Ten dokument zawiera informacje dotyczące planowania wdrożenia, konfigurowania infrastruktury i wdrażania programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lokalnie).

## <a name="finance-and-operations-components"></a>Składniki programu Finance and Operations

Aplikacji Finance and Operations zawiera trzy główne składniki:

- Serwer obiektów aplikacji (AOS)
- Analiza biznesowa (BI)
- Raportowanie finansowe/Management Reporter

Te składniki są zależne od następującego oprogramowania systemowego:

- Microsoft Windows Server 2016
- Microsoft SQL Server 2016 z dodatkiem SP1, który ma następujące funkcje:

    - Włączono funkcję pełnotekstowego przeszukiwania indeksu.
    - SQL Server Reporting Services (SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > Aplikacja nie będzie działać, jeśli nie włączono funkcji wyszukiwania pełnotekstowego.

- SQL Server Management Studio
- Samodzielne wystąpienie platformy Microsoft Azure Service Fabric
- Windows PowerShell w wersji 5.0 lub nowszej
- Active Directory Federation Services (AD FS) w środowisku Windows Server 2016

  Kontroler domeny musi zawierać system Windows Server 2012 R2 lub nowszy z poziomem funkcjonalności domeny 2012 R2 lub wyższym

  Aby uzyskać więcej informacji na temat poziomów funkcjonalnych domen, zobacz: 
  - [Co to są poziomy funkcjonalności w usłudze Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Omówienie poziomów funkcjonalności w usłudze Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Usługa Lifecycle Services

Składniki oprogramowania Finance and Operations są rozprowadzane za pośrednictwem usługi Microsoft Dynamics Lifecycle Services (LCS). Przed rozpoczęciem wdrażania należy kupić kluczy licencji za pośrednictwem kanału [umów dla przedsiębiorstw](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) i skonfigurować lokalny projekt w usłudze LCS. Wdrożenia można inicjować tylko za pośrednictwem usługi LCS. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania lokalnych projektów w usłudze LCS, zobacz [Tworzenie projektu lokalnego w usłudze Lifecycle Services](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Uwierzytelnianie

Lokalna aplikacja współpracuje z usługą AD FS. Aby umożliwić komunikację z usługą LCS, należy również skonfigurować usługę Azure Active Directory (Azure AD).

## <a name="standalone-service-fabric"></a>Samodzielne wystąpienie platformy Service Fabric

Program Finance and Operations korzysta z samodzielnego wystąpienia platformy Service Fabric. Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją platformy Service Fabric](/azure/service-fabric/).

## <a name="infrastructure"></a>Infrastruktura

Program Finance and Operations jest przeznaczony do pracy w architekturze hiperkonwergentnej. Konfiguracja sprzętowa zawiera następujące składniki:

- Samodzielny klaster usługi Service Fabric oparty na maszynach wirtualnych (VM) z systemem Windows Server 2016
- SQL Server (obsługiwane są konfiguracje klastrowanego serwera SQL i zawsze włączonego serwera SQL)
- AD FS do uwierzytelniania
- Udział plikowy bloku komunikatów serwera (SMB) w wersji 3 pliku do przechowywania plików
- Opcjonalnie: Microsoft Office Server 2017

Aby uzyskać więcej informacji, zobacz [Wymagania systemowe](../get-started/system-requirements.md) i Wytyczne szacowania zapotrzebowania na elementy infrastruktury.

### <a name="hardware-layout"></a>Układ sprzętu

Zaplanuj infrastrukturę i klaster usługi Service Fabric zgodnie z zalecanymi wielkościami podanymi w dokumencie [Szacowanie zapotrzebowania na sprzęt dla środowisk lokalnych](../get-started/hardware-sizing-on-premises-environments.md). Aby uzyskać więcej informacji dotyczących sposobu planowania klastra platformy Service Fabric, zobacz [Planowanie i przygotowywanie wdrożenia samodzielnego klastra usługi Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

Poniższa tabela pokazuje przykładowy układ sprzętu. Ten przykład jest używany przez cały temat do ilustrowania konfiguracji.

> [!NOTE]
> Główny węzeł klastra usługi Service Fabric musi mieć przynajmniej trzy węzły. W tym przykładzie jako typ węzła głównego wyznaczono **OrchestratorType**.

| Przeznaczenie maszyny                                 | Nazwa maszyny    | Adres IP    |
|-------------------------------------------------|-----------------|---------------|
| Kontroler domeny                               | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| Serwer plików                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| Zawsze włączony klaster serwera SQL                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Klient                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Klaster platformy Service Fabric/serwer obiektów aplikacji 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Klaster platformy Service Fabric/serwer obiektów aplikacji 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Klaster platformy Service Fabric/serwer obiektów aplikacji 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Klaster platformy Service Fabric/Orchestrator 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Klaster platformy Service Fabric/Orchestrator 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Klaster platformy Service Fabric/Orchestrator 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Klaster platformy Service Fabric/węzeł programu Management Reporter | SQLAOSMR1       | 10.179.108.18 |
| Klaster platformy Service Fabric/węzeł usługi SSRS                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Konfiguracja

### <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania muszą być spełnione następujące wymagania wstępne. Konfiguracja tych wstępnie wymaganych składników jest poza zakresem tego dokumentu.

- Usługa Active Directory Domain Services (AD DS) zainstalowana i skonfigurowana w sieci.
- Wdrożona usługa AD FS.
- Zainstalowane oprogramowanie SQL Server, SSRS i Management Studio.

### <a name="overview"></a>Przegląd

W celu skonfigurowania infrastruktury programu Finance and Operations trzeba wykonać następujące kroki.

1. Zaplanowanie nazwy domeny i stref DNS
2. Zaplanowanie i pozyskanie certyfikatów
3. Zaplanowanie kont użytkowników i usług
4. Utworzenie stref DNS i dodanie rekordów A
5. Dołączenie maszyn wirtualnych do domeny
6. Dodanie wstępnie wymaganego oprogramowania do maszyn wirtualnych
7. Pobranie skryptów konfiguracji z usługi LCS
8. Opisanie konfiguracji
9. Zainstalowanie certyfikatów
10. Skonfigurowanie samodzielnego klastra platformy Service Fabric
11. Skonfigurowanie połączenia z usługą LCS dla dzierżawy
12. Skonfigurowanie magazynu plików
13. Skonfigurowanie programu SQL Server
14. Skonfigurowanie baz danych
15. Zaszyfrowanie poświadczeń
16. Ustaw format SSRS
17. Skonfigurowanie usługi AD FS

### <a name="plan-your-domain-name-and-dns-zones"></a>Zaplanowanie nazwy domeny i stref DNS

Zalecamy, aby dla produkcyjnej instalacji serwera AOS używać publicznie zarejestrowanej nazwy domeny. W ten sposób będzie ona dostępna spoza sieci, jeśli jest wymagany dostęp z zewnątrz.

Na przykład jeśli domeną Twojej firmy jest contoso.com, to strefą programu Finance and Operations (lokalnego wdrożenia) może być d365ffo.onprem.contoso.com, a nazwy hostów mogą być następujące:

- ax.d365ffo.onprem.contoso.com w przypadku komputerów z serwerem AOS
- sf.d365ffo.onprem.contoso.com dla klastra usługi Service Fabric

### <a name="plan-and-acquire-your-certificates"></a>Zaplanowanie i pozyskanie certyfikatów

W celu zabezpieczenia klastra usługi Service Fabric i wszystkich wdrażanych aplikacji są wymagane certyfikaty SSL (Secure Sockets Layer). W środowiskach produkcyjnych i piaskownicy zalecamy uzyskanie certyfikatów z urzędów certyfikacji (CA), takich jak [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/), [Symantec](https://www.websecurity.symantec.com/ssl-certificate), [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate) lub [GlobalSign](https://www.globalsign.com/en/ssl/). Jeśli w domenie skonfigurowano [usługi certyfikatów w usłudze Active Directory](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx) (AD CS), można tworzyć certyfikaty za pomocą tych usług. Każdy certyfikat musi zawierać klucz prywatny utworzony na potrzeby wymieniania się kluczami oraz być możliwy do wyeksportowania do pliku wymiany informacji osobistych (pfx).

Certyfikatów z podpisem własnym można używać tylko do celów testowych. Dla wygody skrypty konfiguracji zawierają skrypty, które generują i eksportują certyfikaty z podpisem własnym. Jak już wspomniano, tych certyfikatów można używać tylko do celów testowych.

| Cel                                      | Wyjaśnienie | Dodatkowe wymagania |
|----------------------------------------------|-------------|-------------------------|
| Certyfikat SSL programu SQL Server                   | Ten certyfikat jest używany do szyfrowania danych przesyłanych przez sieć między wystąpieniem programu SQL Server a aplikacją kliencką. | <p>Nazwa domeny certyfikatu powinna być identyczna z w pełni kwalifikowaną nazwą domeny (FQDN) wystąpienia programu SQL Server lub odbiornika.</p><p>Na przykład jeśli odbiornik SQL jest umieszczony na maszynie DAX7SQLAOSQLA, nazwą DNS certyfikatu jest DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Certyfikat serwera usługi Service Fabric            | Ten certyfikat jest używany do zabezpieczania komunikacji między węzłami platformy Service Fabric. Ten certyfikat jest również używany jako certyfikat serwera przestawiany urządzeniu klienckiemu, które się łączy z klastrem. | <p>Nazwa domeny certyfikatu musi odpowiadać strefie DNS, gdzie znajdują się serwer AOS i usługa Service Fabric.</p><p>Na przykład nazwą domeny certyfikatu może być \*.onprem.contoso.com or \*.contoso.com.</p><p>W przypadku używania certyfikatu z symbolem wieloznacznym znak wieloznaczny dotyczy tylko jednego poziomu. Poddomena o alternatywnej nazwie podmiotu (SAN) musi być zastosowana do certyfikatu, jeśli istnieje więcej niż jeden poziom, tak jak \*. contoso.com w poprzednim przykładzie.</p> |
| Certyfikat klienta usługi Service Fabric            | Ten certyfikat jest używany przez klientów do wyświetlania klastra platformy Service Fabric i zarządzania nim. | |
| Certyfikat szyfrowania                     | Ten certyfikat jest używany do szyfrowania poufnych informacji, takich jak hasło programu SQL Server i hasła kont użytkowników. | <p>Klucza certyfikatu należy używać do szyfrowania danych (10), natomiast nie wolno używać do uwierzytelniania serwera ani uwierzytelniania klienta.</p><p>Aby uzyskać więcej informacji, zobacz [Zarządzanie wpisami tajnymi w aplikacjach platformy Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| Certyfikat SSL serwera AOS                          | <p>Ten certyfikat jest używany jako certyfikat serwera przestawiany urządzeniu klienckiemu uzyskującemu dostęp do witryny internetowej serwera obiektów aplikacji. Służy również do włączania certyfikatów usługi Windows Communication Foundation (WCF)/protokołu Simple Object Access Protocol (SOAP).</p><p>Do tego celu można użyć certyfikatu serwera usługi Service Fabric, jeśli zawiera on symbol wieloznaczny.</p> | <p>Nazwa domeny certyfikatu musi odpowiadać strefie DNS, gdzie znajdują się serwer AOS i usługa Service Fabric.</p><p>Na przykład nazwą domeny certyfikatu może być \*.d365ffo.onprem.contoso.com, \*.onprem.contoso.com lub \*.contoso.com.</p><p>W przypadku używania certyfikatu z symbolem wieloznacznym znak wieloznaczny dotyczy tylko jednego poziomu. Poddomena o nazwie SAN musi być zastosowana do certyfikatu, jeśli istnieje więcej niż jeden poziom, tak jak \*. contoso.com w poprzednim przykładzie.</p> |
| Certyfikat uwierzytelniania sesji           | Ten certyfikat jest używany przez serwer AOS do zabezpieczania informacji w sesji użytkownika. | Jest to również certyfikat **udziału plików**, który będzie używany podczas wdrażania z usługi LCS. |
| Certyfikaty szyfrowania i podpisywania danych | Te certyfikaty są używane przez serwer obiektów aplikacji do szyfrowania poufnych informacji. | |
| Certyfikat klienta raportowania finansowego       | Ten certyfikat jest używany do zabezpieczania komunikacji między węzłami usług raportowania finansowego a serwerem AOS. | |
| Certyfikat raportowania                        | Ten certyfikat jest używany do zabezpieczania komunikacji między usługą SSRS a serwerem AOS. | |
| Certyfikat lokalnego agenta           | <p>Ten certyfikat jest używany do zabezpieczania komunikacji między lokalnym agentem zainstalowanym w lokalnym wdrożeniu a usługą LCS.</p><p>Ten certyfikat umożliwia lokalnemu agentowi działanie w imieniu dzierżawy usługi Azure AD oraz komunikowanie się z usługą LCS, aby zorganizować i monitorować wdrożenie.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>Zaplanowanie kont użytkowników i usług

Aby program Finance and Operations (lokalne wdrożenie) działał, należy utworzyć kilka kont użytkowników lub usług. Należy utworzyć kombinację kont usług zarządzanych grupowo (gMSA), kont domen i kont programu SQL. W poniższej tabeli przedstawiono konta użytkowników, ich przeznaczenie oraz przykładowe nazwy, które będą używane w tym temacie.

| Konto użytkownika                                            | Typ           | Cel | Nazwa użytkownika |
|---------------------------------------------------------|----------------|---------|-----------|
| Konto usługi aplikacji raportowania finansowego         | gMSA           |         | Contoso\\svc-FRAS$ |
| Konto usługi procesu raportowania finansowego             | gMSA           |         | Contoso\\svc-FRPS$ |
| Konto usługi projektanta aplikacji ClickOnce raportowania finansowego | gMSA           |         | Contoso\\svc-FRCO$ |
| Konto usługi serwera obiektów aplikacji                                     | gMSA           | Tego użytkownika należy utworzyć dla spodziewanych przyszłych potrzeb. Planujemy wdrożyć współdziałanie serwera AOS z kontami gMSA w przyszłych wersjach. Tworząc tego użytkownika podczas instalacji, pomagasz zagwarantować bezproblemową migrację do konfiguracji z kontami gMSA. | Contoso\\svc-AXSF$ |
| Konto usługi serwera obiektów aplikacji                                     | Konto domeny | Serwer AOS korzysta z tego użytkownika w wydaniu GA. | Contoso\\AXServiceUser |
| Administrator bazy danych SQL serwera AOS                                   | Użytkownik aplikacji SQL       | Program Finance and Operations wykorzystuje tego użytkownika do uwierzytelniania w programie SQL\*. Ten użytkownik również zostanie zastąpiony użytkownikiem gMSA w przyszłych wersjach. | AXDBAdmin |
| Konto usługi agenta lokalnego wdrożenia                  | gMSA           | To konto jest używane przez lokalnego agenta do organizowania wdrożenia w różnych węzłach. | Contoso\\Svc-LocalAgent$ |

\* Nazwa i hasło użytkownika wykorzystywane do uwierzytelniania w programie SQL są zabezpieczone, ponieważ są zaszyfrowane i przechowywane w udziale plików.

### <a name="create-dns-zones-and-add-a-records"></a>Utworzenie stref DNS i dodanie rekordów A

Usługa DNS jest zintegrowana z usługą AD DS. Umożliwia organizowanie i znajdowanie zasobów w sieci oraz zarządzanie nimi. Utwórz strefę wyszukiwania do przodu w usłudze DNS oraz rekordy dla nazwy hosta serwera AOS i klastra usługi Service Fabric. W tej przykładowej konfiguracji nazwą strefy DNS jest d365ffo.onprem.contoso.com, a nazwy rekordów A/hostów są następujące:

- **ax**.d365ffo.onprem.contoso.com w przypadku komputerów z serwerem AOS
- **sf**.d365ffo.onprem.contoso.com dla klastra usługi Service Fabric

#### <a name="add-a-dns-zone"></a>Dodanie strefy DNS

W celu dodania strefy DNS należy wykonać następującą procedurę.

1. Zaloguj się na komputerze kontrolera domeny, kliknij przycisk **Start** i uruchom Menedżera DNS, wpisując **dnsmgmt.msc**.
2. Kliknij prawym przyciskiem myszy nazwę kontrolera domeny, a następnie wybierz kolejno opcje **Nowa strefa** \> **Dalej**.
3. Wybierz opcję **Strefa podstawowa**.
4. Pozostaw zaznaczone pole wyboru **Przechowuj strefę w usłudze Active Directory (dostępne, jeśli serwer DNS jest zapisywalnym kontrolerem domeny)**, a następnie kliknij przycisk **Dalej**.
5. Zaznacz opcję **Do wszystkich serwerów DNS uruchomionych na kontrolerach domeny w tej domenie: Contoso.com**, a następnie kliknij przycisk **Dalej**.
6. Zaznacz opcję **Strefa wyszukiwania do przodu**, a następnie kliknij przycisk **Dalej**.
7. Wprowadź nazwę strefy, która ma być używana w Twojej instalacji, a następnie kliknij przycisk **Dalej**. Na przykład wpisz **d365ffo.onprem.contoso.com**.
8. Zaznacz opcję **Nie zezwalaj na aktualizacje dynamiczne**, a następnie kliknij przycisk **Dalej**.

#### <a name="set-up-an-a-record-for-aos"></a>Skonfigurowanie rekordu A dla serwera AOS

W nowej strefie DNS utwórz jeden rekord A o nazwie **ax.d365ffo.onprem.contoso.com** dla **każdego** węzła klastra platformy Service Fabric typu **AOSNodeType**. Nie twórz rekordów A dla pozostałych typów węzłów.

1. Kliknij prawym przyciskiem nową strefę i wybierz polecenie **Nowy host**.
2. Wprowadź nazwę i adres IP węzła usługi Service Fabric (np. 10.179.108.12), a następnie kliknij przycisk **Dodaj hosta**.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Skonfigurowanie rekordu A dla narzędzia Orchestrator

W nowej strefie DNS utwórz rekord A o nazwie **sf.d365ffo.onprem.contoso.com** dla **każdego** węzła klastra platformy Service Fabric typu **OrchestratorType**. Nie twórz rekordów A dla pozostałych typów węzłów.

1. Kliknij prawym przyciskiem nową strefę i wybierz polecenie **Nowy host**.
2. Wprowadź nazwę i adres IP węzła usługi Service Fabric (np. 10.179.108.15), a następnie kliknij przycisk **Dodaj hosta**.

#### <a name="join-vms-to-the-domain"></a>Dołączenie maszyn wirtualnych do domeny

Dołącz każdą maszynę wirtualną do domeny, wykonując kroki opisane w temacie [Jak dołączyć system Windows Server 2016 do domeny usługi Active Directory](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). Alternatywnie użyj skryptu programu Windows PowerShell.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
Po dołączeniu maszyn wirtualnych do domeny dodaj konta usługi serwera obiektów aplikacji (Contoso\svc-AXSF$, Contoso\svc-AXSF$) do lokalnej grupy administratorów. Informacje o tym, jak to zrobić, zawiera artykuł [Dodawanie członka do grupy lokalnej](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx).

#### <a name="disable-user-access-control"></a>Wyłączenie funkcji kontroli dostępu użytkowników 

Wykonaj następujący skrypt, aby wyłączyć funkcję kontroli dostępu użytkowników w **każdym** węźle platformy Service Fabric.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> Po pomyślnym zakończeniu działania skryptu należy ponownie uruchomić węzeł.

#### <a name="add-prerequisite-software-to-vms"></a>Dodanie wstępnie wymaganego oprogramowania do maszyn wirtualnych

W poniższej tabeli wymieniono wstępnie wymagane składniki oprogramowania, które należy zastosować do maszyn w każdym typie węzła.

> [!NOTE]
> Po zainstalowaniu składników konieczne będzie ponowne uruchomienie komputera.

| Typ węzła | Składnik | Polecenie |
|-----------|-----------|---------|
| Serwer AOS       | SNAC — sterownik ODBC | Zobacz [Sterownik Microsoft ODBC 13.1 dla programu SQL Server — Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| Serwer AOS       | Microsoft .NET Framework w wersji 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| Serwer AOS       | Microsoft .NET Framework w wersji 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| Serwer AOS       | Internetowe usługi informacyjne (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| Serwer AOS       | Microsoft SQL Server Management Studio 2016 | |
| Serwer AOS       | Pakiety redystrybucyjne programu Microsoft Visual C++ dla programu Microsoft Visual Studio 2013 | Zobacz [Pakiety redystrybucyjne programu Microsoft Visual C++ dla programu Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |
| Serwer AOS       | Pakiet redystrybucyjny programu Microsoft Access Database Engine 2010 | Zobacz [Pakiet redystrybucyjny programu Microsoft Access Database Engine 2010](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| ANALIZA BIZNESOWA        | .NET Framework w wersji 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| ANALIZA BIZNESOWA        | .NET Framework w wersji 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| ANALIZA BIZNESOWA        | Microsoft SQL Server 2016 z dodatkiem SP1 | |
| ANALIZA BIZNESOWA        | Management Studio 2016 | |
| ANALIZA BIZNESOWA        | SQL Server Reporting Services 2016 w trybie **natywnym** | |
| MR        | .NET Framework w wersji 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | .NET Framework w wersji 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Pakiety redystrybucyjne programu Visual C++ dla programu Visual Studio 2013 | Zobacz [Pakiety redystrybucyjne programu Microsoft Visual C++ dla programu Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |

#### <a name="download-setup-scripts-from-lcs"></a>Pobranie skryptów konfiguracji z usługi LCS

Przygotowaliśmy kilka skryptów usprawniających proces instalacji. Wykonaj następujące kroki, aby pobrać skrypty konfiguracji z usługi LCS.

1. Zaloguj się w usłudze LCS (<https://lcs.dynamics.com/v2>).
2. Na pulpicie nawigacyjnym kliknij kafelek **Biblioteka zasobów wspólnych**.
3. Kliknij kartę **Model**.
4. W siatce zaznacz wiersz **Dynamics 365 for Operations — skrypty lokalnego wdrażania**.
5. Kliknij przycisk **Wersje** i pobierz najnowsze wersje skryptów.

### <a name="describe-your-configuration"></a>Opisanie konfiguracji

Ten rozdział zawiera informacje o skryptach, które należy wykonać. Skrypty są omówione w kolejności, w jakiej należy je uruchomić. Aby uruchomić skrypty, wypełnij plik szablonu umieszczony w ścieżce $(downloadPath)\\ConfigTemplate.xml. Plik ConfigTemplate.xml opisuje klastry usługi Service Fabric, certyfikaty używane do ich konfigurowania oraz konta, którym należy przyznać dostęp do odpowiednich certyfikatów. W przykładzie poniżej wartości są wypełniane dla przykładowej infrastruktury opisanej w tym temacie. Plik szablonu zostanie użyty w następnym rozdziale.

#### <a name="create-the-domain-account-for-a-service-user"></a>Utworzenie konta domeny dla użytkownika usługi

Uruchom następujące polecenie, aby utworzyć konto użytkownika domeny contoso\\AXServiceUser.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>Utworzenie kont gMSA

1. Zmień katalog na **$(DownloadPath)** i uruchom następujące polecenie programu Windows PowerShell.

    > [!NOTE]
    > Ten skrypt nie powoduje utworzenia użytkowników. Zamiast tego zostaną wyświetlone polecenia, które należy uruchomić ręcznie na komputerze kontrolera domeny.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Skopiuj dane wyjściowe polecenia do okna programu Windows PowerShell. Upewnij się, że podziały wierszy są usunięte, a następnie uruchom wiersze poleceń na komputerze kontrolera domeny usługi Active Directory, używając podwyższonego poziomu uprawnień (kliknij prawym przyciskiem myszy i wybierz polecenie **Uruchom jako administrator**).
3. Uruchom następujący skrypt na komputerze kontrolera domeny usługi Active Directory w celu sprawdzania, czy konta zostały pomyślnie utworzone. Koniecznie uruchom skrypt po zmianie wzorca odpowiadającego konwencji nazewnictwa kont usług.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Uruchom skrypt Export-AddGMSAsONVMScript.ps1 na komputerze klienckim. Ten skrypt spowoduje wygenerowanie skryptów uruchamianych na każdej maszynie wirtualnej platformy Service Fabric i dodanie ich do folderów odpowiadających nazwom poszczególnych maszyn wirtualnych.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>Zatrzymanie usługi IIS

Za pomocą protokołu Remote Desktop Protocol (RDP) nawiąż połączenie z każdą maszyną wirtualną usługi Service Fabric, a następnie wykonaj ręczne czynności opisane w temacie [Uruchamianie lub zatrzymywanie serwera sieci Web (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). Alternatywnie użyj następującego skryptu programu Windows PowerShell z protokołem RDP, aby nawiązać połączenia ze wszystkimi maszynami wirtualnymi platformy Service Fabric.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
_Oprogramowanie IIS powinno być zainstalowane, ale wyłączone, ponieważ w produkcie istnieją pewne zależności od bibliotek DLL oprogramowania IIS._

### <a name="install-certificates"></a>Zainstalowanie certyfikatów

1. Jeśli certyfikaty wymienione wcześniej w tym temacie zostały pozyskane od prawidłowego urzędu certyfikacji, wprowadź nazwy plików .pfx i odciski palców dla certyfikatów w pliku ConfigTemplate.xml. W atrybucie **generateSelfSignedCert** ustaw wartość **False**, a w atrybucie **exportable** również wartość **False**. Skopiuj pliki .pfx do folderu $(DownloadPath)\\InfrastructureScripts\\Certs.
2. Jeśli używasz certyfikatu z podpisem własnym (tylko do celów testowych), uruchom następujący skrypt. Aby utworzyć certyfikaty z podpisem własnym, w pliku ConfigTemplate.xml, upewnij się, że atrybut **generateSelfSignedCert** ma wartość **True**, a atrybut **exportable** wartość również **True**. Skrypt spowoduje aktualizację pliku XML o odciski palców dla certyfikatów.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Wyeksportuj nowe certyfikaty z kluczem prywatnym (plik .pfx). Użyj następującego skryptu, aby wygenerować i uruchomić polecenia eksportu w programie Windows PowerShell. Pliki .pfx zostaną umieszczone w folderze Certs.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Certyfikaty muszą być zainstalowane i obecne w folderze cert:\\CurrentUser\\My. Ponadto certyfikaty muszą być możliwe do wyeksportowania.

    Jeśli używasz certyfikatów z podpisem własnym, przejdź do następnego rozdziału. Nie musisz wykonywać tej procedury.

4. Po wyeksportowaniu lub skopiowaniu plików .pfx do folderu $(DownloadPath)\\InfrastructureScripts\\Certs uruchom następujące polecenia, aby wygenerować skrypty, które zostaną umieszczone w folderach odpowiadających maszynom wirtualnym.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. Skopiuj skrypty w poszczególnych folderach do maszyn wirtualnych odpowiadających nazwom folderów.
6. Na każdej maszynie wirtualnej uruchom następujące skrypty w podanej kolejności.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Skonfigurowanie samodzielnego klastra platformy Service Fabric

1. Uruchom następujące polecenie, aby wygenerować plik ClusterConfig.json.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    Aby uzyskać więcej informacji zobacz, [Krok 1B: Tworzenie klastra wielokomputerowego](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster), [Zabezpieczenia klastra autonomicznego w systemie Windows przy użyciu certyfikatów X.509](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security) i [Tworzenie klastra autonomicznego w systemie Windows Server](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Pobierz [pakiet instalacyjny samodzielnego wystąpienia usługi Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) na jeden z węzłów z platformą Service Fabric. Po pobraniu pliku zip odblokuj go, klikając prawym przyciskiem myszy, a następnie klikając polecenie **Właściwości**. W oknie dialogowym zaznacz pole wyboru **Odblokuj** w prawym dolnym rogu.
3. Skopiuj plik zip do jednego z węzłów w klastrze platformy Service Fabric i rozpakuj go.
4. Uruchom następujące polecenia w celu utworzenia reguły zapory dla ruchu przychodzącego na portach 443 i 445 we wszystkich węzłów.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Uruchom następujące polecenia w celu utworzenia reguły zapory dla ruchu przychodzącego na porcie 60 tylko dla węzła z usługą SSRS.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Skopiuj plik ClusterConfig.json do lokalizacji instalacji samodzielnej platformy Service Fabric zawierającej rozpakowany plik.
7. Przejdź do lokalizacji instalacji z rozpakowanym plikiem w narzędziu Windows PowerShell, korzystając z podwyższonego poziomu uprawnień, i uruchom następujące polecenie, aby sprawdzić działanie pliku ClusterConfig.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Jeśli test wypadnie pomyślnie, uruchom następujące polecenie, aby wdrożyć klaster.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. Po utworzeniu klastra otwórz eksploratora usługi Service Fabric na dowolnym komputerze klienckim w celu sprawdzenia poprawności instalacji:

    1. Zainstaluj certyfikat klienta usługi Service Fabric w folderze CurrentUser\\My, jeśli jeszcze nie jest zainstalowany.
    2. Wybierz kolejno opcje **Ustawienia programu Internet Explorer** \> **Tryb zgodności z** i wyczyść pole wyboru **Wyświetlaj witryny intranetowe w trybie zgodności**.
    3. Przejdź do strony`https://sf.d365ffo.onprem.contoso.com:19080`, gdzie sf.d365ffo.onprem.contoso.com to nazwa hosta klastra usługi Service Fabric określonego w strefie. Jeśli nie jest skonfigurowane rozpoznawanie nazw w usłudze DNS, użyj adresu IP komputera.
    4. Zaznacz certyfikat klienta. Zostanie wyświetlona strona **Eksplorator usługi Service Fabric**.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Skonfigurowanie połączenia z usługą LCS dla dzierżawy

Wdrażanie i serwisowanie programu Finance and Operations są organizowane za pośrednictwem usługi LCS przy użyciu lokalnego agenta. W celu ustanowienia połączenia między usługą LCS a dzierżawą programu Finance and Operations należy skonfigurować certyfikat, który umożliwia lokalnemu agentowi działanie w imieniu dzierżawy usługi Azure AD (na przykład Contoso.Onmicrosoft.com).

Użyj certyfikatu lokalnego agenta pozyskanego z urzędu certyfikacji lub certyfikatu z podpisem własnym wygenerowanego za pomocą skryptów.

Certyfikaty autoryzujące usługę LCS mogą dodawać tylko posiadacze kont z rolą katalogu Administrator globalny. Domyślnie globalnym administratorem katalogu będzie osoba, która rejestruje się w usłudze Microsoft Office 365 w imieniu organizacji.

> [!NOTE]
> Certyfikat należy skonfigurować dokładnie jeden raz dla każdej dzierżawy. Wszystkie środowiska lokalne mogą używać tego samego certyfikatu do łączenia się z usługą LCS.

1. Pobierz i zainstaluj najnowszą wersję programu Azure PowerShell na komputerze klienckim. Aby uzyskać więcej informacji, zobacz [Instalowanie i konfigurowanie programu Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Zaloguj się w [portalu Azure dla klientów](https://portal.azure.com), aby sprawdzić, czy masz rolę katalogu Administrator globalny.
3. Uruchom następujący skrypt ze ścieżki $(DownloadPath)\\InfrastructureScripts.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Skonfigurowanie magazynu plików

Należy skonfigurować dwa udziały plików SMB 3.0 o wysokiej dostępności. Aby uzyskać informacje dotyczące włączania obsługi protokołu SMB 3.0, zobacz [Rozszerzenia zabezpieczeń protokołu SMB](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
Funkcja bezpiecznego negocjowania dialektu nie może wykrywać ani zapobiegać obniżaniu wersji z SMB 2.0 lub 3.0 na SMB 1.0. W związku z tym oraz w celu pełnego wykorzystania możliwości szyfrowania SMB stanowczo zalecamy wyłączenie serwera protokołu SMB 1.0.

> [!NOTE]
> Aby zagwarantować, że dane są chronione, gdy znajdują się w stanie spoczynkowym w środowisku, na każdym komputerze należy włączyć szyfrowanie dysków funkcją BitLocker. Aby uzyskać informacje dotyczące sposobu włączania funkcji BitLocker, zobacz [BitLocker: Jak wdrożyć w systemie Windows Server w wersji 2012 i nowszych](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- Udział plików, w którym są przechowywane dokumenty użytkownika przekazane do serwera AOS (na przykład \\\\DAX7SQLAOFILE1\\aos-storage).
- Udział plików, w którym są przechowywane najnowsze pliki kompilacji i konfiguracji umożliwiające zorganizowanie wdrożenia (na przykład \\\\DAX7SQLAOFILE1\\agent)

    > [!NOTE]
    > Ścieżka udziału plików powinna być jak najkrótsza, aby uniknąć przekroczenia maksymalnej dozwolonej długości ścieżki dla plików, które będą umieszczane w udziale.

1. Na komputerze z udziałem plików uruchom następujące polecenie.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Skonfigurowanie udziału plików \\\\DAX7SQLAOFILE1\\aos-storage

2. W Menedżerze serwera wybierz kolejno opcje **Usługi plików i magazynowania** \> **Udziały**.
3. Kliknij kolejno opcje **Zadania** \> **Nowy udział**, aby utworzyć nowy udział o nazwie **aos-storage**.
4. Przyznaj uprawnienia **Modyfikacja** każdemu komputerowi w klastrze usługi Service Fabric, z wyjątkiem komputera **OrchestratorNodeType**.
5. Przyznaj uprawnienia **Modyfikacja** użytkownikowi w domenie serwera AOS (contoso\\AXServiceUser) i użytkownikowi posiadającemu konto gMSA (contoso\\svc-AXSF).

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Skonfigurowanie udziału plików \\\\DAX7SQLAOFILE1\\agent

6. Wróć do Menedżera serwera i wybierz kolejno opcje **Usługi plików i magazynowania** \> **Udziały**.
7. Kliknij kolejno opcje **Zadania** \> **Nowy udział**, aby utworzyć nowy udział o nazwie **agent**.
8. Przyznaj uprawnienia **Pełna kontrola** użytkownikowi posiadającemu konto gMSA wobec lokalnego agenta wdrożenia (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Skonfigurowanie programu SQL Server

1. Zainstaluj program SQL Server 2016 z dodatkiem SP1 w układzie wysokiej dostępności — albo jako klastry serwera SQL zawierające sieć magazynowania (SAN), albo jako konfigurację ciągłego włączenia.  Upewnij się, że składniki **aparat bazy danych, Reporting Services, wyszukiwanie pełnotekstowe** i **narzędzia do zarządzania** są już zainstalowane.
> [!NOTE]
> Upewnij się, że funkcja ciągłego włączenia serwera SQL jest skonfigurowana zgodnie z opisem w temacie [Wybieranie początkowej strony synchronizacji danych (kreatory zawsze włączonych grup dostępności)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards), i wykonaj czynności opisane w temacie [Aby ręcznie przygotować pomocnicze bazy danych](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Uruchom usługę SQL jako użytkownik domeny.
3. Pobierz certyfikat SSL z urzędu certyfikacji, aby skonfigurować program Finance and Operations. Do celów testowych można utworzyć i wykorzystywać certyfikat z podpisem własnym.

**Certyfikat z podpisem własnym dla wystąpienia klastrowanego serwera SQL**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Certyfikat z podpisem własnym dla wystąpienia zawsze włączonego serwera SQL**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. Używając certyfikatu, wykonaj kroki opisane w temacie [Jak włączyć szyfrowanie SSL w wystąpieniu programu SQL Server przy użyciu aplikacji Microsoft Management Console](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console), aby skonfigurować obsługę protokołu SSL w programie SQL Server.
5. Dla każdego węzła w klastrze wykonaj następujące czynności. Upewnij się, że można dokonać zmian w nieaktywnym węźle, a następnie przełączyć do niego awaryjnie po wprowadzeniu zmian.

    1. Zaimportuj certyfikat do folderu LocalMachine\\My.
    2. Przyznaj certyfikatowi uprawnienia do konta usługi używanego do uruchamiania usługi SQL. W programie Microsoft Management Console (MMC) kliknij prawym przyciskiem myszy certyfikat (certlm.msc), a następnie kliknij kolejno polecenia **Zadania** \> **Zarządzaj kluczami prywatnymi**.
    3. Dodaj odcisk palca certyfikatu do klucza rejestru HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\Certificate.
    4. W menedżerze konfiguracji programu Microsoft SQL Server w ustawieniu **ForceEncryption** zaznacz wartość **Tak**.

6. Wyeksportuj klucz publiczny certyfikatu (plik .cer) i zainstaluj go w zaufanym katalogu głównym każdego węzła usługi Service Fabric.

### <a name="configure-the-orchestratordata-database"></a>Skonfigurowanie bazy danych OrchestratorData

1.  Utwórz pustą bazę danych i nadaj jej nazwę **OrchestratorData**. Ta baza danych jest używana przez lokalnego agenta do organizowania wdrożeń.
2.  Przyznaj lokalnemu agentowi gMSA (svc LocalAgent$) uprawnienie **db\_owner** wobec bazy danych:

    1. W drzewie rozwiń węzeł z nazwą serwera, rozwiń kolejno węzły **Zabezpieczenia** \> **Nazwy logowania**, a następnie kliknij prawym przyciskiem myszy i wybierz polecenie **Nowe nazwy logowania**.

        ![Polecenie Nowa nazwa logowania](./media/OPSetup_01_NewLogin.png)


    2. Wyszukaj konto usługi **svc-LocalAgent$**. Kliknij opcję **Lokalizacje**, wybierz opcję **Cały katalog**, a następnie kliknij opcję **Typy obiektów** i wybierz opcję **Konto usługi**.

        ![Okno dialogowe Wybierz użytkownika, konto usługi lub grupę](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. W ustawieniu **Przypisz rolę serwera** zaznacz opcję **Publiczny**.
    4. Przypisz uprawnienie roli bazy danych **db\_owner** wobec bazy danych OrchestratorData.

### <a name="configure-the-finance-and-operations-database"></a>Skonfigurowanie bazy danych programu Finance and Operations

1. Zaloguj się w usłudze LCS (<https://lcs.dynamics.com/v2>).
2. Na pulpicie nawigacyjnym kliknij kafelek **Biblioteka zasobów wspólnych**.
3. Kliknij kartę **Model**. 
4. W siatce kliknij wiersz **Lokalne wdrożenie programu Dynamics 365 for Operations Enterprise Edition — dane demonstracyjne**, aby pobrać plik zip.
5. Plik .zip zawiera pliki .bak puste i z danymi demonstracyjnymi. Na podstawie swoich konkretnych potrzeb pobierz odpowiedni plik .bak. Na przykład jeśli potrzebujesz danych demonstracyjnych, przywróć plik AxBootstrapDB_Demodata.bak. 
6. Przywróć plik bazy danych AxBootstrapDB_DemoData.bak.
7. Zmień nazwę bazy danych na **AXDBRAIN**.
8. W przywróconej bazie danych wykonaj następujące zapytania.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Zaktualizuj pliki bazy danych:

    1. Kliknij bazę danych prawym przyciskiem myszy i wybierz polecenie **Właściwości**.
    2. Kliknij opcję **Pliki**, aby zmienić właściwości pliku bazy danych.
    3. W polu **Rozmiar początkowy (MB)** wprowadź wartość większą niż 5120.

        ![Okno dialogowe Właściwości bazy danych](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. W wierszu **AXDBBuild\_Data** w polu **Automatyczne zwiększanie/Maksymalizuj** ustaw wartość **200** megabajtów (MB).
    5. W wierszu **AXDBBuild\_Log** w polu **Automatyczne zwiększanie/Maksymalizuj** ustaw wartość **500** MB.

        ![Okno dialogowe Zmiana automatycznego zwiększania](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Utwórz nowego użytkownika, który ma włączone uwierzytelnianie w programie SQL (axdbadmin).
6. Za pomocą informacji w tabeli poniżej zamapuj użytkowników i role bazy danych.

    | Użytkownik             | Typ    | Rola bazy danych |
    |------------------|---------|---------------|
    | svc-AXSF$        | gMSA    | db\_owner     |
    | svc-LocalAgent$  | gMSA    | db\_owner     |
    | svc-FRPS$        | gMSA    | db\_owner     |
    | svc-FRAS$        | gMSA    | db\_owner     |
    | axdbadmin        | SqlUser | db\_owner     |

7. Przyznaj użytkownikowi svc-AXSF$ i użytkownikowi programu SQL axdbadmin dostęp do następujących ról w bazie danych tempdb:

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. W programie Management Studio uruchom następujące polecenia języka Transact SQL (T-SQL):

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Uruchom następujące polecenie:
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>Skonfigurowanie bazy danych raportowania finansowego

1.  Utwórz pustą bazę danych i nadaj jej nazwę **FinancialReporting**.
2.  Za pomocą informacji w tabeli poniżej zamapuj użytkowników i role bazy danych.

    | Użytkownik             | Typ | Rola bazy danych |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_owner     |
    | svc-FRPS$        | gMSA | db\_owner     |
    | svc-FRAS$        | gMSA | db\_owner     |

### <a name="encrypt-credentials"></a>Zaszyfrowanie poświadczeń

1. Na dowolnym komputerze klienckim zainstaluj certyfikat szyfrowania w folderze LocalMachine\\Mój magazyn certyfikatów.
2. Przyznaj bieżącemu użytkownikowi uprawnienie odczytu klucza prywatnego tego certyfikatu.
3. Utwórz plik Credentials.json, jak pokazano poniżej.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** jest hasłem użytkownika szyfrowanej domeny dla użytkownika domeny serwera AOS (contoso\\axserviceuser).
    - **SqlUser** jest szyfrowaną nazwą użytkownika programu SQL (axdbadmin), który ma dostęp do bazy danych programu Finance and Operations (AXDBRAIN), a **SqlPassword** jest szyfrowanym hasłem programu SQL.

4. Skopiuj plik .json do udziału plików SMB \\\\AX7SQLAOFILE1\\agent\\Credentials\\Credentials.json.
5. Zaktualizuj plik Credentials.json o zaszyfrowane wartości.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. W pliku Credentials.json zastąp parametr **\<encryptedDomainUserPassword\>** hasłem szyfrowanej domeny.
    2. Zastąp parametr **\<encryptedSqlUser\>** szyfrowaną nazwą użytkownika SQL programu Finance and Operations.
    3. Zastąp parametr **\<encryptedSqlPassword\>** hasłem użytkownika SQL programu Finance and Operations.
    
### <a name="set-up-ssrs"></a>Ustaw format SSRS

1.  Przed rozpoczęciem upewnij się, że są zainstalowane wymagane wstępnie składniki wymienione na początku tego tematu.
2.  Wykonaj czynności podane w temacie [Konfigurowanie usług SQL Server Reporting Services dla wdrożenia lokalnego](../analytics/configure-ssrs-on-premises.md).

### <a name="configure-ad-fs"></a>Skonfigurowanie usługi AD FS

Zanim będzie można wykonać tę procedurę, należy wdrożyć usługę AD FS w systemie Windows Server 2016. Aby uzyskać informacje dotyczące sposobu wdrażania usługi AD FS, zobacz [Przewodnik wdrażania usługi AD FS w systemach Windows Server 2016 i 2012 R2](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

Program Finance and Operations wymaga dodatkowej konfiguracji, wykraczającej poza standardową konfigurację usługi AD FS. W poniższych krokach program Windows PowerShell jest uruchamiany na komputerze z zainstalowaną usługą roli usługi AD FS. Konto użytkownika musi mieć wystarczające uprawnienia do administrowania usługą AD FS. Na przykład użytkownik musi mieć konto administratora domeny.

1. Skonfiguruj taki identyfikator usługi AD FS, aby pasował do wystawcy tokenów usługi AD FS.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Należy wyłączyć funkcję Zintegrowane uwierzytelnianie systemu Windows (WIA) dla połączeń z uwierzytelnianiem w intranetach, chyba że usługę AD FS skonfigurowano dla środowisk mieszanych. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania funkcji WIA, tak aby mogła być używana przez usługę AD FS, zobacz [Konfigurowanie używania zintegrowanego uwierzytelniania systemu Windows (WIA) z usługą AD FS w przeglądarkach](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. Na potrzeby logowania adres e-mail użytkownika musi być akceptowanymi danymi wejściowymi uwierzytelniania.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

Aby usługa AD FS ufała programowi Finance and Operations podczas wymiany informacji uwierzytelniających, muszą być zarejestrowane różne wpisy aplikacji w usłudze AD FS w grupie aplikacji AD FS. Aby przyspieszyć proces instalacji i zmniejszyć ryzyko błędów, można użyć następującego skryptu rejestracji. Skopiuj skrypt Publish-ADFSApplicationGroup.ps1 i katalog D365FO-OP do komputera, na którym jest zainstalowana usługa roli usługi AD FS. Następnie uruchom skrypt przy użyciu konta użytkownika, takiego jak konto administratora, które ma wystarczające uprawnienia do administrowania usługą AD FS. Aby uzyskać więcej informacji dotyczących sposobu użycia skryptu, zapoznaj się z dokumentacją podaną w skrypcie. Zanotuj identyfikatory klientów zawarte w danych wyjściowych, ponieważ trzeba będzie podać te informacje w usłudze LCS na późniejszym etapie.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

Konsola zarządzania usługą AD FS powinna wyglądać jak na ilustracji poniżej. Aby otworzyć Menedżera serwera, kliknij kolejno opcje **Narzędzia** \> **Zarządzanie programem AD FS**, a następnie w dolnej części widoku drzewa po lewej stronie kliknij opcję **Grupy aplikacji**. Kliknij dwukrotnie grupę aplikacji, aby wyświetlić więcej szczegółów.

![Właściwości grupy aplikacji](./media/OPSetup_05_ApplicatioGroupProperties.png)

Na koniec w ramach podstawowego sprawdzania działania upewnij się, że możesz uzyskać dostęp adresu URL konfiguracji usługi OpenID wewnątrz usługi AD FS w węźle platformy Service Fabric o typie **AOSNodeType**, przechodząc do strony `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` w przeglądarce sieci web. Jeśli zostanie wyświetlony komunikat informujący, że witryna nie jest bezpieczna, oznacza to, że nie dodano certyfikatu SSL usługi AD FS do magazynu zaufanych głównych urzędów certyfikacji. Ten etap jest opisany w podręczniku wdrażania usługi AD FS. Jeśli możesz uzyskać dostęp do adresu URL, zostanie zwrócony plik JSON (JavaScript Object Notation) zawierający konfigurację usługi AD FS i będzie widać, że adres URL usługi AD FS jest zaufany.

Po wykonaniu tej czynności konfigurowanie infrastruktury jest zakończone. W poniższych rozdziałach opisano sposób przechodzenia do usługi [LCS](https://lcs.dynamics.com) w celu skonfigurowania łącznika i wdrożenia środowiska Dynamics 365 for Finance and Operations.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Konfigurowanie łącznika i instalowanie lokalnego agenta

1. Zaloguj się w usłudze [LCS](https://lcs.dynamics.com/) i otwórz projekt lokalnej implementacji.
2. W menu hamburgerowym kliknij polecenie **Ustawienia projektu**.

    ![Polecenie Ustawienia projektu](./media/OPSetup_06_ProjectSettings.png)

3. Kliknij opcję **Łączniki On-premises**.
4. Kliknij przycisk **Dodaj**, aby utworzyć nowy łącznik.
5. Na karcie **Konfiguracja infrastruktury hosta** pobierz instalatora agenta.

    ![Przycisk Pobierz instalatora agenta na karcie Konfiguracja infrastruktury hosta](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Sprawdź, czy plik .zip jest odblokowany. Kliknij prawym przyciskiem myszy plik, wybierz polecenie **Właściwości**, a następnie wybierz opcję **Odblokuj**.
7. Rozpakuj instalatora agenta na jednym z węzłów platformy Service Fabric o typie **OrchestratorType**.
8. Na karcie **Konfigurowanie agenta** wprowadź ustawienia konfiguracji.
9. Zapisz konfigurację, a następnie kliknij przycisk **Pobierz konfiguracje** i pobierz plik konfiguracji localagent-config.json.

    ![Przycisk Pobierz konfiguracje na karcie Konfigurowanie agenta](./media/OPSetup_08_DownloadConfigurations.png)

10. Skopiuj plik localagent config.json do komputera, na którym znajduje się pakiet instalatora agenta.
11. W oknie wiersza polecenia wpisz następujące polecenie, przechodząc do folderu zawierającego instalatora agenta.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > Użytkownik wykonujący to polecenie musi mieć uprawnienia **db\_owner** wobec bazy danych OrchestratorData.
    
12. Po pomyślnym zainstalowaniu lokalnego agenta przejdź z powrotem do lokalnego łącznika w usłudze LCS.
13. Na karcie **Weryfikacja konfiguracji** kliknij przycisk **Agent komunikatów**. Spowoduje to przetestowanie łączności między usługą LCS a lokalnym agentem. Po pomyślnym ustanowieniu połączenia strona będzie wyglądała tak jak na ilustracji poniżej.

     ![Weryfikacja agenta](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Wdrożenie środowiska Dynamics 365 for Finance and Operations (lokalnie)

1. Przejdź do swojego lokalnego projektu w usłudze LCS, a następnie wybierz kolejno opcje **Środowisko**, **Piaskownica** i **Konfiguruj**.
2. Wybierz odpowiednią wartość w polu **Topologia środowiska** i przejdź przez kolejne kroki w kreatorze, aby zainicjować wdrożenie.
3. Lokalny agent odbierze żądanie wdrożenia, rozpocznie wdrażanie, a po zakończeniu pracy wyśle zwrotną informację do usługi LCS.

