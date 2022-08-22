---
title: Podpisz plik MPOS .appx certyfikatem podpisywania kodu
description: W tym artykule wyjaśniono sposób podpisywania aplikacji MPOS za pomocą certyfikatu podpisywania kodu.
author: josaw1
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-09-2019
ms.custom: 28021
ms.openlocfilehash: bcf558b4b375078ed24777417e92b1c852f4c0eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282814"
---
# <a name="sign-the-mpos-appx-file-with-a-code-signing-certificate"></a>Podpisz plik MPOS .appx certyfikatem podpisywania kodu

[!include [banner](../includes/banner.md)]

Aby zainstalować program Modern POS (MPOS), musisz podpisać aplikację MPOS przy użyciu certyfikatu podpisywania kodu od zaufanego dostawcy i zainstalować ten sam certyfikat na wszystkich komputerach, na których program MPOS jest zainstalowany w zaufanym folderze głównym bieżącego użytkownika.

Aby podpisać aplikację MPOS certyfikatem, użyj jednej z tych opcji w pliku **Retail SDK\\Build tool\\Customization.settings**:

- Dodaj część zadania Zabezpieczanie pliku w krokach Azure DevOps kompilacji i przekaż certyfikat, aby zabezpieczyć zadanie pliku. Użyj zmiennej ścieżki wyjściowej bezpiecznego zadania pliku jako parametru w pliku Customization.settings.

    > [!NOTE]
    > Zadanie Plik bezpieczny nie obsługuje certyfikatu chronionego hasłem. Musisz usunąć hasło przed przekazaniem tego zadania. Ponieważ certyfikat jest przekazany do zadania bezpiecznego systemu plików w systemie Azure, możesz usunąć hasło tylko dla tego kroku. Należy jednak omówić usunięcie hasła z ekspertami ds. zabezpieczeń, aby ustalić, czy ta akcja jest poprawna dla projektu. Nie usuwaj hasła certyfikatu w innych scenariuszach.
- Użyj certyfikatu, który jest w systemie plików. W tym celu pobierz lub wygeneruj certyfikat i umieść go w systemie plików, w którym jest uruchomiona kompilacja. Agent obsługiwany przez firmę Microsoft lub użytkownik kompilacji powinien mieć dostęp do tej ścieżki i pliku.
- Użyj odcisku palca, aby odszukać certyfikat w sklepie i zalogować się za pomocą tego certyfikatu.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Użyj zadania bezpiecznego pliku na użytek podpisu aplikacji universal Windows Platform

> [!NOTE]
> Można także użyć narzędzia Azure Key W celu przechowywania certyfikatu i używania narzędzia podpisywania systemu Azure, aby podpisać plik appx programu Modern POS i instalatorów samoobsługi. Aby uzyskać przykładowe skrypty potoków i dodatkowe informacje, zobacz [temat Konfigurowanie potoku kompilacji w celu Azure DevOps generowania pakietów samoobsługowych sieci sprzedaży](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

Korzystanie z zadania bezpiecznego pliku jest zalecanym rozwiązaniem w przypadku podpisywania aplikacji universal Windows Platform (UWP). Aby uzyskać więcej informacji dotyczących podpisywania pakietów, zobacz temat [Konfiguruj podpisywanie pakietu](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Ten proces pokazano na poniższym obrazku.

![Przepływ podpisywania aplikacji MPOS.](media/POSSigningFlow.png)

> [!NOTE]
> Obecnie opakowanie OOB obsługuje podpisywanie tylko pliku appx, dlatego ten proces nie podpisuje różnych instalatorów samoobsługi, takich jak MP RSSU, RSSU i HWS. Podpis należy podpisać ręcznie za pomocą narzędzia SignTool lub innych narzędzi do podpisywania. Certyfikat używany do podpisywania pliku appx musi być zainstalowany na komputerze, na którym jest zainstalowany program Modern POS.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Kroki konfigurowania certyfikatu do rejestrowania w potokach systemu Azure

### <a name="certificate-in-the-file-systemsecure-location"></a>Certyfikat w systemie plików/bezpiecznej lokalizacji

Pobierz zadanie [DownloadFile](/visualstudio/msbuild/downloadfile-task) i dodaj je jako pierwszy krok procesu kompilacji. Użycie funkcji bezpiecznego pliku ma tę zaletę, że plik jest szyfrowany i umieszczany na dysku podczas kompilacji, niezależnie od tego, czy potok kompilacji zakończy się pomyślnie, nie powiedzie się czy zostanie anulowany. Plik jest usuwany z lokalizacji pobierania po zakończeniu procesu kompilacji.

1. Pobierz i dodaj zadanie bezpiecznego pliku jako pierwszy krok w potoku kompilacji platformy Azure. Zadanie Zabezpieczenia pliku można pobrać z pliku [DownloadFile](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
1. Przekaż certyfikat do zadania Zabezpieczenia pliku i ustaw nazwę odwołania w obszarze Zmienne wyjściowe, tak jak pokazano na poniższym obrazie.
    > [!div class="mx-imgBorder"]
    > ![Bezpieczny plik zadania.](media/SecureFile.png)
1. Utwórz nową zmienną w potokach Azure, wybierając **nową zmienną** na karcie **Zmienne**.
1. Podaj nazwę zmiennej w polu wartości, na przykład **MySigningCert**.
1. Zapisz zmienną.
1. Otwórz plik **Customization.settings** z aplikacji **RetailSDK\\BuildTools** i zaktualizuj plik **ModernPOSPackageCertificateKeyFile** przy użyciu nazwy zmiennej utworzonej w potoku (krok 3). Na przykład:

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Ten krok jest wymagany, jeśli certyfikat nie jest chroniony hasłem. Jeśli certyfikat jest chroniony hasłem, należy wykonać następujące kroki.
    
1. Jeśli chcesz, aby plik MPOS .appx był opatrzony znacznikiem czasu podczas podpisywania go certyfikatem, otwórz plik **Retail SDK\\Build tool\\Customization.settings** i zaktualizuj zmienną **ModernPOSPackageCertificateTimestamp** za pomocą dostawcy znacznika czasu (np, `http://timestamp.digicert.com`).
1. Na karcie **Zmienne** potoku dodaj nową zmienną tekstową bezpieczną. Ustaw nazwę **MySigningCert.secret** i ustaw wartość hasła dla certyfikatu. Wybierz ikonę blokady, aby zabezpieczyć zmienną.
1. Dodaj zadanie **skryptu programu Powershell** do potoku (po pobraniu bezpiecznego pliku i przed krokiem kompilacji). Podaj nazwę **wyświetlaną** i ustaw typ jako **w tekście**. Skopiuj i wklej następujące elementy do sekcji skryptu.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

1. Otwórz plik **Customization.settings** z aplikacji **RetailSDK\\BuildTools** i zaktualizuj plik **ModernPOSPackageCertificateThumbprint** wartością odcisku palca certyfikatu.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
Aby uzyskać szczegółowe informacje dotyczące pobierania odcisku palca dla certyfikatu, zobacz temat [Pobierania odcisku palca certyfikatu](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Pobierz lub wygeneruj certyfikat w celu ręcznego podpisania aplikacji MPOS przy użyciu zestawu msbuild w zestawie SDK

Jeśli pobrany lub wygenerowany certyfikat jest używany do podpisywania aplikacji MPOS, zaktualizuj węzeł **ModernPOSPackageCertificateKeyFile** w pliku **BuildTools\\Customization.settings**, aby wskazywał lokalizację pliku pfx (**$(SdkReferencesPath)\\appxsignkey.pfx**). Na przykład:

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

W tym przypadku nazwą pliku certyfikatu jest **appxsignkey.pfx**, znajdującego się w folderze **Retail SDK\\Reference** folder.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Użyj odcisku palca, aby podpisać aplikację MPOS

Jeśli do podpisywania aplikacji MPOS jest używać odcisku palca, należy zainstalować certyfikat lokalnie. Zaktualizuj wartość odcisku palca w węźle **ModernPOSPackageCertificateThumbprint** w pliku **BuildTools\\Customization.settings**.

Ta opcja będzie działać, jeśli użytkownik kompilacji jest użytkownikiem lokalnym. Jeśli jednak do wygenerowania kompilacji są używani agenci Azure DevOps, agent może nie mieć uprawnień dostępu do sklepu certyfikacji, aby używać certyfikatu do podpisywania lub komputer kompilacji nie ma zainstalowanego certyfikatu. W tym przypadku obejście ma na celu zmianę użytkownika kompilacji na użytkownika lokalnego i zainstalowanie certyfikatu w tym polu. Jednak ta opcja nie będzie działać, jeśli nie masz dostępu administratora do tego pola.

> [!NOTE]
> Jeśli do podpisania aplikacji jest używana opcja pliku .pfx lub opcja zadania bezpiecznego pliku, pozostaw węzeł **ModernPOSPackageCertificateThumbprint** w **Customization.settings** pusty. Jeśli jest używana opcja odcisku palca, pozostaw pusty **ModernPOSPackageCertificateKeyFile**. Jeśli obie wartości zostaną zaktualizowane, kompilacja nie powiedzie się.

### <a name="certification-renewal"></a>Odnowienie certyfikacji

### <a name="renew-a-certificate-from-trusted-ca"></a>Odnowienie certyfikatu od zaufanego urzędu certyfikacji

Skontaktuj się z urzędu certyfikacji w celu procesu odnowienia certyfikatu. W przypadku zaufanego certyfikatu po stronie MPOS nie jest wymagana żadna akcja.

### <a name="renew-a-self-signed-certificate"></a>Odnowienie certyfikatu podpisanego samodzielnie

Nie używaj przykładowego certyfikatu dostępnego w zestawie Retail SDK do produkcji. Może być wykorzystywany wyłącznie do celów rozwojowych. Nie można odnowić przykładowego certyfikatu contoso, a przykładowy certyfikat dołączony do zestawu Retail SDK w wersji 10.0.16 lub wcześniejszej wygaśnie 31 grudnia 2020. Jeśli ten certyfikat lub certyfikat z podpisem własnym został użyty do podpisania niestandardowego wystąpienia w programie Modern POS, istnieje możliwość, że program Modern POS po tej dacie nie będzie poprawnie działać.
 
### <a name="impact"></a>Wpływ
 
Jeśli powyższe powyższe zasady są spełnione, problem, który będzie napotkany, wynika z tego, że instalator nie będzie mógł uruchomić systemu po 31 grudnia 2020 roku. Funkcje programu Modern POS mogą nie być możliwe w zależności od używanych firmowych zasad IT. Jest konieczne przetestowanie tego tematu przez tymczasową zmianę daty na datę przyszłą, aby określić wpływ na organizację.
 
### <a name="steps-to-determine-the-issue"></a>Kroki, aby ustalić problem
 
1.  Za pomocą ustawień systemu Windows zmień datę i czas zegara komputera w roku 2021.
2.  Sprawdź, czy można otworzyć program Modern POS, może nastąpić logowanie i czy można zakończyć transakcję.
3.  Sprawdź, czy instalatora samoobsługowego programu Modern POS można uruchomić, a jeśli tak, instalacja zakończy się pomyślnie.
4.  Przywróć prawidłową datę i czas ustawień zegara systemu Windows.
 
Jeśli wszystkie te kroki zostaną ukończone bez żadnych problemów, będzie można wykonać bieżący certyfikat z przeszłości 31 grudnia 2020.  
 
### <a name="steps-going-forward"></a>Kroki naprzód 

Zdecydowanie zaleca się odnowienie wcześniej użytego certyfikatu. Zdecydowanie zaleca się uzyskanie nowego certyfikatu. Aby to zrobić, należy wykonać jedną z poniższych czynności:
 
- **Preferowany** — uzyskiwanie certyfikatu podpisywania kodu od zaufanego urzędu certyfikacji.

- **Nie jest preferowany** — generowanie certyfikatu podpisywania kodu automatycznie do użycia. Zwykle jest on używany tylko w celach programistywnych w domenie i nie jest zalecany do produkcji. 

- **Dostępne jako tymczasowe rozwiązanie** — użyj odnowionego certyfikatu podpisywania kodu Contoso. Zwykle jest to używane do testowania, więc nie zaleca się wdrażania ich w środowisku produkcyjnym.
 
Następnie wygeneruj nowy dostosowany pakiet programu Modern POS, który jest podpisany przy użyciu tego certyfikatu uzyskanego z jednej z powyższych akcji. W zależności od certyfikatu należy wykonać jedną z poniższych czynności:
 
- W przypadku korzystania z nowego, zaufanego certyfikatu (lub nowego, podpisanego samodzielnie) konieczne będzie zainstalowanie nowego certyfikatu na każdym urządzeniu. Następnie należy pobrać nowo utworzony pakiet programu Modern POS (instalatora), odinstalować istniejącą aplikację, a następnie ponownie zainstalować nowy pakiet programu Modern POS. Aktywację urządzeń programu Modern POS trzeba przeprowadzić na każdym urządzeniu.

- W przypadku korzystania z odnowionego certyfikatu Contoso trzeba zainstalować nowy certyfikat na każdym urządzeniu i zainstalować pakiet Modern POS (instalator). Nie jest wymagane odinstalowywanie, należy jednak ponownie zainstalować na urządzeniu. Pamiętaj, że aktywacja urządzenia programu Modern POS nie będzie wymagana. Ta opcja jest rozwiązaniem tymczasowym. Tej opcji należy użyć tylko w celu uniknięcia ponownej aktywacji i rozwiązania problemu przed uzyskaniem nowego zaufanego certyfikatu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
