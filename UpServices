# Lista de serviços a serem excluídos
$excludedServices = @('sppsvc', 'RemoteRegistry', 'gupdate', 'WbioSrvc')

# Lista de serviços automáticos, excluindo os serviços excluídos
$automaticServices = Get-Service | Where-Object { $_.StartType -eq 'Automatic' -and $_.Name -notin $excludedServices }

# Verifica se algum serviço automático não está em execução, exceto os serviços excluídos
foreach ($service in $automaticServices) {
    if ($service.Status -ne 'Running') {
        Write-Host "O serviço $($service.DisplayName) está parado."
        
        # Se desejar, você pode iniciar o serviço automaticamente descomentando a linha abaixo
        # Start-Service -Name $service.Name
    }
}

Write-Host "Done"
