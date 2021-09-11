_G.Ver = 'v1.0.0 alpha'
_G.MaintenanceTHUB = false
_G.KickReason = "점검중"
_G.Title = "텍스트키 HUB ".._G.Ver
_G.DiscordTHUB = ApfRjc5wha

local http = game:GetService('HttpService') 

if toClipboard then
	toClipboard(_G.DiscordTHUB)
end

local req = (syn and syn.request) or (http and http.request) or http_request
if req then
	req({
		Url = 'http://127.0.0.1:6463/rpc?v=1',
		Method = 'POST',
		Headers = {
			['Content-Type'] = 'application/json',
			Origin = 'https://discord.com'
		},
		Body = http:JSONEncode({
			cmd = 'INVITE_BROWSER',
			nonce = http:GenerateGUID(false),
			args = {code = _G.DiscordTHUB}
		})
	})
end
