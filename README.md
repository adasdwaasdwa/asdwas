local aimActive = false  -- Estado da mira
local enemy = {x = 400, y = 300} -- Posição do inimigo (exemplo)
local aim = {x = 0, y = 0}  -- Posição da mira

function love.update(dt)
    if aimActive then
        aim.x = enemy.x
        aim.y = enemy.y
    end
end

function love.draw()
    -- Desenha o inimigo
    love.graphics.setColor(1, 0, 0)  -- Vermelho
    love.graphics.circle("fill", enemy.x, enemy.y, 20)
    
    -- Desenha a mira
    if aimActive then
        love.graphics.setColor(0, 1, 0)  -- Verde
        love.graphics.circle("line", aim.x, aim.y, 30)
    end
end

function love.keypressed(key)
    if key == "e" then
        aimActive = true  -- Ativar mira
    elseif key == "q" then
        aimActive = false -- Desativar mira
    end
end
